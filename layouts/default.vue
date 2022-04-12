<template>
  <v-app dark>
    <background></background>
    <v-main>
        <Nuxt />
    </v-main>

  </v-app>
</template>

<script>
import Background from "../components/background";
export default {
  name: 'DefaultLayout',
  components: {Background},
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>
<style>

html {
  overflow-y: hidden;
}
</style>
