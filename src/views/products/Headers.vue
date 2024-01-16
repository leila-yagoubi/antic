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

  <v-app-bar dense app color="transparent" flat>
      <v-container>
        <v-row align="left">
         
          
          
          
            <v-tabs left align-tabs="start" v-model="tab" class="custom-tabs d-none d-sm-flex">
              <v-tab class="custom-title" >antic</v-tab>
        <v-tab v-for="(item, index) in items" :key="index" @click="selectTab(index)">
          {{ item }}
        </v-tab>
      </v-tabs>
        
          <v-spacer />
          <div>
            <v-btn icon dark class="ml-2 d-sm-flex d-none">
      <v-avatar size="30">
        <v-img src="@/assets/Union.png" color="black"></v-img>
      </v-avatar>
    </v-btn>
          </div>
        </v-row>
      </v-container>
    </v-app-bar>


  <!-- <v-app-bar dense app color="transparent" flat>
    <v-app-bar-title class="custom-title">
      antic
      
    </v-app-bar-title><v-tabs v-model="tab" class="custom-tabs d-none d-sm-flex">
        <v-tab v-for="(item, index) in items" :key="index" @click="selectTab(index)">
          {{ item }}
        </v-tab>
      </v-tabs>

    <v-spacer></v-spacer>

    <v-app-bar-nav-icon @click="drawer = !drawer" class="d-sm-none" color="white"></v-app-bar-nav-icon>

    <v-spacer></v-spacer>

    <v-btn icon dark class="ml-2 d-sm-flex d-none">
      <v-avatar size="30">
        <v-img src="@/assets/Union.png" color="black"></v-img>
      </v-avatar>
    </v-btn>
  </v-app-bar> -->
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
    display: flex;
    align-items: center;
    color: #A06056;
    font-size: 30px;
    font-family: Merriweather;
    font-weight: 700;
    line-height: 25px;
    letter-spacing: 2px;
  
  }

  .custom-tabs {
    color: #706458;
    font-size: 18px;
    font-family: Varta;
    font-weight: 400;
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
