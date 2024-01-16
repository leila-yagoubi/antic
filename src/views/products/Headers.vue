<template>
  <v-navigation-drawer class="custom-drawer" v-model="drawer" app>
    <v-list>
      <v-list-item-group v-model="tab">
        <v-list-item v-for="(item, index) in items" :key="index" @click="selectTab(index)">
          {{ item }}
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-navigation-drawer>

  <v-app-bar app color="transparent" flat>
    <v-container>
      <v-row align="center">
        <v-tab class="custom-title" :disabled="isDisabled" >antic</v-tab>
        <v-tabs v-model="tab" class="custom-tabs d-none d-sm-flex" align-tabs="center">
          
          <v-tab v-for="(item, index) in items" :key="index" @click="selectTab(index)">
            {{ item }}
          </v-tab>
        </v-tabs>

        <v-spacer />

        <v-btn icon dark class="ml-2 d-sm-flex d-none">
          <v-avatar size="30">
            <v-img src="@/assets/Union.png" color="black"></v-img>
          </v-avatar>
        </v-btn>
      </v-row>
    </v-container>
  </v-app-bar>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      tab: null,
      items: ['Products', 'Room', 'Services', 'Inspiration'],
    };
  },
  methods: {
    selectTab(index) {
      this.tab = index;
      this.drawer = false;
    },
  },
};
</script>

<style scoped>
/* Larger Screens */
@media only screen and (min-width: 768px) {
  .custom-app-bar {
    background-color: transparent;
    box-shadow: none;
  }

  .custom-title {
    color: #A06056;
    font-size: 30px;
    font-family: Merriweather;
    font-weight: 700;
    line-height: 25px;
    letter-spacing: 2px;
    text-transform: none !important;
  }

  .custom-tabs {
    color: #706458;
    font-size: 18px;
    font-family: Varta;
    font-weight: 400;
    text-transform: none !important;
  }
}

/* Smaller Screens */
@media only screen and (max-width: 768px) {  
  .custom-title {
    font-family: Merriweather;
    font-size: 24px;
    font-weight: 700;
    line-height: 25px;
    letter-spacing: 2px;
    text-align: left;
    color: rgba(255, 255, 255, 1);
  }

  .custom-drawer {
    display: flex;
    justify-content: space-between;
  }

  .custom-tabs {
    display: none; 
  }
}
</style>
