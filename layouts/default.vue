<template>
  <v-app>

    <AppBar/>

    <v-main>
      <nuxt />
    </v-main>

    <v-footer
      :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }} - BRECOMPERU</span>
      <v-spacer/>
      <v-switch v-model="$vuetify.theme.dark" primary label="Dark"></v-switch>
    </v-footer>

  </v-app>
</template>

<script>
export default {
  data () {
    return {
      fixed:false,
      pageName: 'Brecomperu'
    }
  },
  head() {
    const title = this.pageName
    return {
      title,
      meta: [
        {
          hid: "description",
          name: "description",
          content: "desarrollo de software"
        }
      ],
      htmlAttrs: {
        lang: 'es'
      }
    }
  }
}
</script>
