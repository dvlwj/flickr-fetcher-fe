<template>
  <v-container>
    <p v-if="isError" class="red--text text-center full-width">Something is wrong. Please try again later.</p>
    <v-row justify="center" align="center">
      <v-text-field
        v-model="tags"
        autofocus
        background-color="#f1f1f2"
        flat
        full-width
        hide-details
        label="Search by tags"
        prepend-inner-icon="mdi-magnify"
        single-line
        rounded
        type="text"
        class="search-bar"
        @keydown.enter="fetchImages"
      ></v-text-field>
    </v-row>
    <gallery
      :images="this.imageGallery"
    />
  </v-container>
</template>

<script>
import gallery from '~/components/gallery.vue'

export default {
  components: {
    gallery
  },
  data () {
    return {
      isError: false,
      imageGallery: [],
      tags: null
    }
  },
  mounted() {
    this.fetchImages()
  },
  methods: {
    async fetchImages() {
      const url = 'http://localhost:3001/api/flicker/feed'
      const payloadToSend = {
        tags: this.tags
      }
      await this.$axios.post(url,payloadToSend)
      .then(
        (res) => {
          if (res.status === 200) {
            this.isError = false
            this.imageGallery = res.data.items
          } else {
            this.isError = true
          }
        }
      )
      .catch(e => {
        this.isError = true
      })
    }
  }
}
</script>

<style lang="less" scoped>
.full-width {
  width: 100%
}
.search-bar {
  margin: 1em;
}
</style>
