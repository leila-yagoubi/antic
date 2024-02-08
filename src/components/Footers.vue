<template>
  <v-footer class="d-flex flex-column footer ">
    <!-- Content Rows -->
    <div class="footer-content">
      <!-- First Row -->
      <v-row>
        <v-col cols="12" md="2">
          <h4 class="title">antic</h4>
        </v-col>
        <v-col cols="12" md="2">
          <h1 class="column">Products</h1>
          <v-list dense bg-color="rgba(243, 238, 232, 1)">
            <v-list-item v-for="item in products" :key="item">
              <v-list-item-title class="text-caption">{{ item }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-col>
        <v-col cols="12" md="2">
          <h4 class="column">Rooms</h4>
          <v-list dense bg-color="rgba(243, 238, 232, 1)">
            <v-list-item v-for="item in rooms" :key="item">
              <v-list-item-title class="text-caption">{{ item }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-col>
        <v-col cols="12" md="2">
          <h4 class="column">Services</h4>
          <v-list dense bg-color="rgba(243, 238, 232, 1)">
            <v-list-item v-for="item in services" :key="item">
              <v-list-item-title class="text-caption">{{ item }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-col>
        <v-col cols="12" md="2">
          <h1 class="column1">We respect our planet</h1>
          <v-img src="@/assets/lastPicture.png" width="100%"></v-img>
          <p class="text-caption">We’re taking positive steps to reduce our impact on the planet. For us, that means
            retailing responsibly.</p>
          <v-btn append-icon="mdi-chevron-right" variant="text" class="btn mr-14">Learn more</v-btn>
        </v-col>
      </v-row>

      <!-- Social Icons Row -->
      <v-row class="bgTop text-center">
        <v-col cols="12">
          <v-icon class="mr-1">mdi mdi-facebook</v-icon>
          <v-icon class="mr-1">mdi mdi-twitter</v-icon>
          <v-icon class="mr-1">mdi mdi-instagram</v-icon>
          <v-icon class="mr-1">mdi mdi-linkedin</v-icon>
        </v-col>
      </v-row>

      <!-- Copyright Row -->
      <v-row class="mt-5 justify-space-between">
        <v-col cols="12" md="6" class="d-flex align-center ">
          <v-icon class="mr-1">mdi mdi-copyright</v-icon>
          <strong>Copyright {{ new Date().getFullYear() }} Agence Dnd</strong>
        </v-col>
        <v-col cols="12" md="3" class="text-right">
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
  padding: 5% 0% 5% 0%;
}

.footer-content {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.title {
  font-family: Merriweather;
  font-size: 3vw;
  line-height: 25px;
  letter-spacing: 2px;
  text-align: left;
  color: rgb(43, 112, 89);
}

.column {
  font-family: Varta;
  font-size: 1.8vw;
  font-weight: 800;
  line-height: 8vh;
  letter-spacing: -0.20000000298023224px;
  text-align: left;
  color: rgba(83, 75, 66, 1);
}

.column1 {
  font-family: Varta;
  font-size: 1.8vw;
  line-height: 4vh;
  letter-spacing: -0.20000000298023224px;
  text-align: left;
  color: rgba(83, 75, 66, 1);
}

.btn {
  font-family: Karla;
  font-size: 1vw;
  font-weight: 700;
  line-height: 25px;
  letter-spacing: 0.30000001192092896px;
  text-align: left;
  justify-content: left;
  color: #24824e;
  padding: 0;
  text-transform: none;
}

.text-caption {
  line-height: 2vh;
  color: rgba(112, 100, 88, 1);
}

.privacy {
  font-family: Varta;
  font-size: 1vw;
  font-weight: 500;
  text-align: left;
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
