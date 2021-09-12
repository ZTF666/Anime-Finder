<template>
  <v-app dark>
    <AppBar />
    <v-main class="primary">
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>

    <v-footer absolute app class="primary">
      <span class="accent--text">&copy; {{ new Date().getFullYear() }}</span>
      <v-spacer></v-spacer>
      <span class="accent--text">Powered by 
        <a class="success--text" href="https://trace.moe/" target="_blank">
          Trace.moe</a></span>
      <v-spacer></v-spacer>
      <span class="accent--text">Made by 
        <a class="secondary--text" href="https://ztfportfolio.web.app/" target="_blank">
        ZTF</a></span>
    </v-footer>
  </v-app>
</template>

<script>

export default {

  data () {
    return {

    }
  }
}
</script>
