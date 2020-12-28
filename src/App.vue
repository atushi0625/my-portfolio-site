<template>
  <v-card class="overflow-hidden">
    <v-app-bar
      absolute
      color="#6A76AB"
      dark
      shrink-on-scroll
      prominent
      src="https://picsum.photos/1920/1080?random"
      fade-img-on-scroll
      scroll-target="#scrolling-techniques-4"
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
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-menu
        bottom
        left
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            icon
            color="yellow"
            v-bind="attrs"
            v-on="on"
          >
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item
            v-for="(item, i) in items"
            :key="i"
          >
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
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
    <v-sheet
      id="scrolling-techniques-4"
      class="overflow-y-auto"
      max-height="1500"
    >
<router-view></router-view>
<router-link to="/">Home</router-link>
<router-link to="/about">About</router-link>
      <v-container style="height: 1500px;"></v-container>
    </v-sheet>
  </v-card>
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
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me 2' },
      ],
    }
  },
  methods: {
    ...mapActions(['toggleSideMenu'])
  }
}
</script>

  
