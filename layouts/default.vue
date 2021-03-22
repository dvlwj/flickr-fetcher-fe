<template>
  <v-app>
    <v-main>
      <v-container
        fluid
        class="px-12"
      >
        <nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
    >
      <v-row align="center" justify="center">
        <span>
          Made with 💗 using <a href="https://nuxtjs.org/" target="_blank" rel="noopener noreferrer">NuxJS</a> and <a href="https://expressjs.com/" target="_blank" rel="noopener noreferrer">ExpressJS</a> with Flickr API
        </span>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      fixed: true,
    }
  }
}
</script>

<style scoped>

  .v-footer {
    padding: 1em;
  }
</style>
