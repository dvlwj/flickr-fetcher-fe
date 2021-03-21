<template>
  <v-app>
    <v-main>
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
    >
      <v-row align="center" justify="center">
        <span>Created with 💗 using NuxJS and ExpressJs with Flickr API</span>
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
