<template>
  <v-sheet
    height="400"
    class="overflow-hidden"
    style="position: relative;"
  >

    <v-navigation-drawer
      v-model="$store.state.drawer"
      absolute
      temporary
    >
      <v-list-item>
        <v-list-item-avatar>
          <v-img src="https://randomuser.me/api/portraits/men/78.jpg"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>Atsushi Sato</v-list-item-title>
        </v-list-item-content>
      </v-list-item>


      <v-list dense>
      <v-divider></v-divider>
        <v-list-title
          v-for="item in items"
          :key="item.title"
          :to="item.link"

        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-title>
      </v-list>
    </v-navigation-drawer>
  </v-sheet>
</template>

<script>
  export default {
      data(){
          return {
              items: [
                { title: 'HOME',  icon: 'mdi-view-dashboard', link: {name: 'Home'} },
                { title: 'ABOUT',  icon: 'mdi-forum', link: {name: 'About'} },
             ],

          }

      }
         
  }
