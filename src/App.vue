<template>
<v-app>
    <v-app-bar
      absolute
      color="#6A76AB"
      dark
      app
      src="https://picsum.photos/1920/1080?random"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(100,115,201,.7), rgba(25,32,72,.7)"
        ></v-img>
      </template>

      <v-app-bar-nav-icon @click="toggleSideMenu"></v-app-bar-nav-icon>

      <v-toolbar-title>Atsushi's Site</v-toolbar-title>


      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon 
        x-large
        color="blue"
        >mdi-twitter</v-icon>
      </v-btn>

          
      <v-btn icon >
        <v-icon x-large>mdi-instagram</v-icon>
      </v-btn>

      <v-menu>
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            icon
            color="yellow"
            v-bind="attrs"
            v-on="on"
            >
            <v-icon x-large>mdi-github</v-icon>
          </v-btn>
        </template>
      </v-menu>
      
      <template v-slot:extension>
        <v-tabs align-with-title>
          <v-tab>HOME</v-tab>
          <v-tab>ABOUT</v-tab>
          <v-tab>WORKS</v-tab>
        </v-tabs>
      </template>
    </v-app-bar>
    <SideNav />

    <v-main>
<router-view></router-view>
    </v-main>

<router-link to="/">Home</router-link>
<router-link to="/about">About</router-link>

  </v-app>
</template>

<script>
import SideNav from './components/SideNav'
import { mapActions } from 'vuex'
export default {
  name: 'App',
  components: {
    SideNav
  },
  data () {
    return {
      items: [
        { title: '' },
        { title: '' },
        { title: '' },
        { title: '' },
      ],
    }
  },
  methods: {
    ...mapActions(['toggleSideMenu'])
  }
}
</script>

  
