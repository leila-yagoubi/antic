<template>
  <!-- Drawer for small screens -->
  <v-navigation-drawer class="custom-drawer" v-model="drawer" app temporary :class="[displayClasses]">
    <v-list>
      <v-list-item-group v-model="tab">
        <v-list-item v-for="(item, index) in items" :key="index" @click="selectTab(index)">
          {{ item.text }}
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-navigation-drawer>

  <v-app-bar app color="transparent" flat class="navbar">

    <v-container fluid>
      <div>
        <v-row align="center" justify="start">


          <!-- Logo and title -->

          <v-toolbar-title class="custom-title d-flex ">
            antic
          </v-toolbar-title>


          <v-spacer />
          <v-app-bar-nav-icon @click="drawer = !drawer" class="d-sm-none drawer"></v-app-bar-nav-icon>

          <v-tabs v-model="tab" class=" d-none d-sm-flex">
            <v-menu v-for="(item, index) in items" :key="index" transition="slide-x-transition" class="d-none d-sm-block">
              <template v-slot:activator="{ props }">
                <v-btn class="custom-tabs " v-bind="props">{{ item.text }}</v-btn>
              </template>
              <!-- Add content for the menu if needed -->

            </v-menu>
          </v-tabs>
          <v-spacer />
          <v-btn class=" d-none d-sm-block   " @click="contactUs">
            <v-avatar> <v-img src="@/assets/Union.png" alt="" /> </v-avatar>
          </v-btn>
        </v-row>
      </div>
    </v-container>

  </v-app-bar>



  <!-- Main content goes here -->
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      tab: null,
      items: [
        { text: "About Us", },
        { text: "Article", },
        {
          text: "Property",
        },
      ],
    };
  },
  methods: {
    selectTab(index) {
      this.tab = index;
      this.drawer = false;
    },
    contactUs() {

    },
  },
};
</script>

<style scoped>
.navbar {
  padding: 3% 0% 0% 6%;
  margin: 0;
}



.custom-title {
  font-family: Lexend;
  font-size: 4vw;
  line-height: 12vh;
  font-weight: 700;
  text-align: left;
  color: #2b7059;

  @media only screen and (max-width: 600px) {
    font-size: 7svb;
  }
}


.custom-tabs {
  width: 7vw;
  height: 5vh;
  text-transform: none !important;
  align-self: center;
  font-family: 'Lexend', sans-serif;
  font-size: 1.2vw;
  font-weight: 300;
  text-align: left;
  color: #386e4f;


}

.drawer {
  color: rgb(255, 255, 255);
  padding-left: 20%;
}

.custom-drawer {
  color: beige;
  background-color: rgb(21, 116, 92);
}
</style>


