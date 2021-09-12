<template>
<div>


<v-app-bar
      :clipped-left="clipped"
      fixed
      app
      color="primary accent--text"
      class="hidden-xs-only"
    >
      <v-img
        alt="Vuetify Logo"
        class="shrink mr-2 img"
        contain
        :src="logo"
        transition="scale-transition"
        width="40"
      />
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn icon class="accent--text"  href="https://github.com/ZTF666/Anime-Finder" target="_blank"><v-icon>mdi-github</v-icon></v-btn>
    </v-app-bar>
    <!-- mobile app bar -->
    <v-app-bar :clipped-left="clipped" fixed app color="primary" class="hidden-sm-and-up">
      <v-img
        alt="Vuetify Logo"
        class="shrink mr-2 img"
        contain
        :src="logo"
        transition="scale-transition"
        width="40"
      />
      <v-toolbar-title v-text="title" class="accent--text" />
      <v-spacer></v-spacer>
      <v-menu left bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-btn icon v-bind="attrs" v-on="on">
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

        <v-list>
          <!-- <v-list-item> -->
          <v-list-item-content>
            <!-- <v-spacer></v-spacer> -->
            <v-btn icon class="accent--text" href="https://github.com/ZTF666/Anime-Finder" target="_blank"><v-icon>mdi-github </v-icon></v-btn>
            
          </v-list-item-content>

          <!-- </v-list-item> -->
        </v-list>
      </v-menu>
    </v-app-bar>

</div>
</template>

<script>
export default {
      head: {
    title: 'Anime Finder 👀',
    meta: [
      {
        hid: 'Find any anime by a screenshot',
        name: 'Anime Finder',
        content: 'look up any anime by using a screenshot !',
      },
    ],
  },
data(){
    return{
      logo: require('../assets/9.png'),
      clipped: false,
      fixed: false,
      title: 'Anime Finder',
    }
    }
}
</script>

<style>

</style>