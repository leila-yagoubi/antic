<template>
  <v-footer class="d-flex flex-column footer ">
    <!-- Content Rows -->
    <div class="footer-content">
      <!-- First Row -->
      <v-row>
        <v-col cols="12" md="3" sm="12">
          <h4 class="title">antic</h4>
        </v-col>
        <v-col cols="12" md="2" sm="3">
          <h1 class="column">Products</h1>
          <p v-for="item in products" :key="item" class="text-caption"> <span class="text">{{ item }}</span></p>

        </v-col>
        <v-col cols="12" md="2" sm="3">
          <h4 class="column">Rooms</h4>
          <p v-for="item in rooms" :key="item" class="text-caption"> <span class="text">{{ item }}</span></p>

        </v-col>
        <v-col cols="12" md="2" sm="3">
          <h4 class="column">Services</h4>
          <p v-for="item in services" :key="item" class="text-caption"> <span class="text">{{ item }}</span></p>

        </v-col>
        <v-col cols="12" md="3" sm="3">
          <h1 class="column mb-5">We respect our planet</h1>
          <v-img src="@/assets/lastPicture.png" width="100%"></v-img>
          <p class="text-caption mt-5"> <span class="text">We’re taking positive steps to reduce our impact on the planet.
              For us, that means
              retailing responsibly.</span></p>
          <v-btn append-icon="mdi-chevron-right" variant="text" class="btn mr-14">Learn more</v-btn>
        </v-col>
      </v-row>

      <!-- Social Icons Row -->
      <v-row class="bgTop text-center social">
        <v-col cols="12"  >
          <v-icon class="mr-1">mdi mdi-facebook</v-icon>
          <v-icon class="mr-1">mdi mdi-twitter</v-icon>
          <v-icon class="mr-1">mdi mdi-instagram</v-icon>
          <v-icon class="mr-1">mdi mdi-linkedin</v-icon>
        </v-col>
      </v-row>

      <!-- Copyright Row -->
      <v-row class="mt-5 justify-space-between">
        <v-col cols="12" md="6" sm="6" class=" social d-flex align-center ">
          <v-icon class="mr-1 ">mdi mdi-copyright</v-icon>
          <strong>Copyright {{ new Date().getFullYear() }} Agence Dnd</strong>
        </v-col>
        <v-col cols="12" md="3" sm="4" class="text-right mt-4">
          <v-row>
            <h4 class="pr-2 privacy">Privacy policy</h4>
            <h4 class="pr-2 pl-2 privacy">Term of service</h4>
            <h4 class="pl-2 privacy">Language</h4>
          </v-row>
        </v-col>
      </v-row>
    </div>
  </v-footer>
</template>

<script>
export default {
  data() {
    return {
      products: ['Furniture', 'Decoration', 'Storage', 'Baby and child', 'Connected home'],
      rooms: ['Living room', 'Dining room', 'Cooked', 'Bedroom', 'Bathroom', 'Office', 'Laundry'],
      services: ['Click and collect', 'Conception', 'Installation', 'Advices', 'Gift card']
    }
  }
}
</script>

<style scoped>
/* Add your styles here */
.footer {
  background-color: #f3eee8;
  padding: 4% 5% 4% 8%;
}



.title {
  font-family: Merriweather;
  font-size: 7svb;
  line-height: 6vh;
  text-align: left;
  color: rgb(43, 112, 89);
}

.column {
  font-family: Varta;
 
  font-size: 4svb;
  font-weight: 800;
  line-height: 8vh;
  letter-spacing: -0.20000000298023224px;
  text-align: left;
  color: rgba(83, 75, 66, 1);
  @media only screen  and (min-width: 600px) and (max-width: 768px ){
    font-size: 3vw;
    line-height: 3vh;
  }
}


.btn {
  font-family: Karla;
  font-size: 2.2vb;
  font-weight: 700;
  line-height: 25px;
  letter-spacing: 0.30000001192092896px;
  text-align: left;
  color: #24824e;
  padding: 0;
  text-transform: none;
  @media only screen  and (min-width: 600px) and (max-width: 768px ){
    font-size: 1.2vw;
    line-height: 3vh;
  }
}

.text-caption {
  line-height: 3vh;
  color: rgba(112, 100, 88, 1);
}

.text {
  font-size: 2.5vb;
  @media only screen  and (min-width: 600px) and (max-width: 768px ){
    font-size:1.5vw;

    line-height: 1vh;
  }
}

.privacy {
  font-family: Varta;
  font-size: 1vw;
  font-weight: 500;
  text-align: left;
  color: rgba(112, 100, 88, 0.7);
  @media only screen  and (min-width: 600px) and (max-width: 768px ){
    font-size:1.5vw;
    line-height: 3vh;
  }
}

.social {
  color: rgba(112, 100, 88, 0.7);
}

@media screen and (max-width: 600px) {
  .footer {
    padding: 30px 10px 44px 10px;
  }

  .footer-content {
    padding: 25px;
  }

  .row {
    flex-direction: column;
  }

  .title {
    align-items: stretch;
    align-self: center;
    text-align: center;
  }

  .footer-section {
    gap: 24px;
  }

  .text-caption {
    font-size: 1vw;
  }
}
</style>
