<template>
  <v-card color="basil">
    <v-card-title class="text-center justify-center py-6">
      <h1 class="font-weight-bold display-3 basil--text">
        My Profile
      </h1>
    </v-card-title>

    <v-tabs
      v-model="tab"
      background-color="transparent"
      color="basil"
      grow
    >
      <v-tab
        v-for="item in items"
        :key="item"
      >
        <h1>{{ item.title }}</h1>
      </v-tab>
    </v-tabs>

    <v-tabs-items v-model="tab">
      <v-tab-item
        v-for="item in items"
        :key="item"
      >
          <h3 class="name">{{item.name}}</h3>

        <v-card
          color="basil"
          flat
        >
      <v-tabs-items v-model="tab">
          <v-tab-item
          v-for="text in texts"
          :key="text"
          >
            <h3 class="message">{{ text.message }}</h3>
            </v-tab-item>
         </v-tabs-items>
        </v-card>
      </v-tab-item>
    </v-tabs-items>
  </v-card>
</template>

<script>
  export default {
    data () {
      return {
        tab: null,
        items: [
          {name: '佐藤　敦', title: '名前', id: 1}, 
          {name: '1989年6月25日', title: '生年月日', id: 2}, 
          {name: '秋田県横手市', title: '出身地', id: 3}, 
          {name: '格闘技', title: '趣味', id: 4},
        ],
        texts: [
          {id: 1, message: 'さとう あつし'},
          {id: 2, message: '31歳'},
          {id: 3, message: '横手焼きそばで有名'},
          {id: 4, message: 'キックボクシング'}
        ]
      }
    },
  }
</script>



<style scoped>
/* Helper classes */
.basil {
  background-color: #FFFBE6 !important;
}
.basil--text {
  color: #356859 !important;
}
h1{
  font-family: serif;
}
.name{
  font-weight: bold;
  font-size: 30px;
}
</style>