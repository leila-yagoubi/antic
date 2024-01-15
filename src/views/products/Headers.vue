<!-- eslint-disable no-undef -->
<template>
 

  <v-navigation-drawer class="custom-drawer" v-model="drawer" app    :class="[
      displayClasses, 
    ]">
    
    <v-list>
      <v-list-item-group v-model="tab">
        <v-list-item v-for="(item, index) in items" :key="index" @click="selectTab(index)">
          {{ item }}
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-navigation-drawer>
<!--    
  
  <v-app-bar app class="custom-app-bar" color="transparent" elevation="0">
    <v-app-bar-nav-icon @click="drawer = true" class="d-sm-none"></v-app-bar-nav-icon>

    <div class="d-flex align-center d-sm-flex ">
      <v-toolbar-title class="custom-title d-none d-flex">antic</v-toolbar-title>

      <v-tabs v-model="tab" class="custom-tabs d-none d-sm-flex">
        <v-tab v-for="(item, index) in items" :key="index" @click="selectTab(index)">
          {{ item }}
        </v-tab>
      </v-tabs>
        
    </div>
    <v-spacer></v-spacer>
 <v-btn density="compact" icon="mdi-comments" variant="outlined" color="white" class="custom-title  d-sm-flex d-none"></v-btn>
    
  </v-app-bar>-->

  <v-app-bar app color="transparent" flat>
    
    <v-toolbar-title class="custom-title ml-15">antic</v-toolbar-title>
    <v-tabs v-model="tab" class="custom-tabs d-none d-sm-flex  mt-1 ">
  <v-tab v-for="(item, index) in items" :key="index" @click="selectTab(index)">
    {{ item }}
  </v-tab>
</v-tabs>

    <v-spacer></v-spacer>
    
   
 <v-app-bar-nav-icon @click="drawer = true" class="d-sm-none " color="white"></v-app-bar-nav-icon>

        

    <v-spacer></v-spacer>
    
    <v-avatar size="30" class="ml-2 d-sm-flex d-none">
      <v-img src="@/assets/Union.png" color="black"></v-img>
    </v-avatar>
    <v-btn icon dark class="">
      <v-icon x-small color="#878A94">fas fa-chevron-down</v-icon>
    </v-btn>
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
    padding: 5vh 10vh 10vh 5%;
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
    word-wrap: break-word;
    
  }

  .custom-tabs {
    color: #706458;
    font-size: 18px;
    font-family: Varta;
    font-weight: 400;
    word-wrap: break-word;
    
  }
}

/* Smaller Screens */
@media only screen and (max-width: 768px) {  
  .custom-title {
    font-family: Merriweather;
    font-size: 24px; /* Adjust as needed */
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
    display: none; /* Optionally hide tabs for small screens */
  }
}
</style>
