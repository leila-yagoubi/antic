<!-- eslint-disable no-undef -->
<template>
  <!-- Drawer for small screens -->
  
  <v-navigation-drawer class="custom-drawer" v-model="drawer" app  temporary  :class="[
      displayClasses, // 'app-drawer--mobile'
    ]">
    
    <v-list>
      <v-list-item-group v-model="tab">
        <v-list-item v-for="(item, index) in items" :key="index" @click="selectTab(index)">
          {{ item }}
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-navigation-drawer>

  <!-- App bar with tabs for larger screens -->
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
 <v-btn density="compact" icon="mdi-comments" variant="outlined" color="white" class="custom-title d-sm-flex d-none"></v-btn>
    
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
.custom-app-bar {
  padding-left: 150px;
  padding-right: 16px;
  padding-top: 16px;
  background-color: transparent;
  box-shadow: none;
}

.custom-title {
  margin-right: 16px;
  color: #A06056;
  font-size: 24px;
  font-family: Merriweather;
  font-weight: 700;
  line-height: 25px;
  letter-spacing: 2px;
  word-wrap: break-word;
}

.custom-tabs {
  color: #706458;
  font-size: 14px;
  font-family: Varta;
  font-weight: 400;
  line-height: 25px;
  word-wrap: break-word;
  margin-left: 16px;
}

@media only screen and (max-width: 768px) {


  .custom-title {
   
font-family: Merriweather;
font-size: 34px;
font-weight: 700;
line-height: 25px;
letter-spacing: 2px;
text-align: left;
color: rgba(255, 255, 255, 1);

}
 .custom-drawer{
  width: 321px;
height: 45px;
top: 41px;
left: 22px;
justify-content: space-between;

 }
}

</style>
