<template>
  <v-container>
    <v-row justify="center" align="center">
      <v-text-field
        autofocus="true"
        background-color="#f1f1f2"
        flat
        full-width
        hide-details
        label="Search"
        prepend-inner-icon="mdi-magnify"
        single-line
        rounded
        type="text"
        class="search-bar"
      ></v-text-field>
    </v-row>
    <gallery/>
  </v-container>
</template>

<script>
import gallery from '~/components/gallery.vue'

export default {
  components: {
    gallery
  }
}
</script>

<style lang="less" scoped>
.search-bar {
  margin: 1em;
}
</style>
