<template>
  <v-row>
    <v-col md="6">
      <h1 class="title1">Be aware of the latest trends</h1>
      <p class="title2">
        Stay informed of new trends, but also of our various offers.
      </p>
      <v-btn class="mt-4 button" variant="text">
        <h6 class="title3">Find out more</h6>
        <v-icon end icon="mdi-chevron-right" size="3svb" color="var(--Terracotta, #2b7059)"></v-icon>
      </v-btn>
    </v-col>
    <v-col>
      <v-row align="center" class="search-row ">
        <v-col md="8" cols="8">
          <v-text-field outlined dense filled solo flat rounded density="compact" variant="solo" class="search-field "
            single-line hide-details>

            <span class="search">Search for the location you want!</span>
          </v-text-field>
        </v-col>
        <v-col md="4" cols="4">
          <v-btn class="btn  text-center">Search <v-icon class="icon " size="3svb" icon="mdi-chevron-right"></v-icon>
          </v-btn>
        </v-col>
      </v-row>
    </v-col>
    <!-- Right column - Subscription form -->

  </v-row>
</template>

<script>
export default {
  data() {
    return {
      email: "",
    };
  },
  methods: {
    subscribe() {
      // Add your subscribe logic here
      console.log("Subscribed with email:", this.email);
    },
  },
};
</script>

<style scoped>
.newsletter {
  background-color: rgb(255, 255, 255);
}

.custom-text-field {
  min-height: auto !important;
  background-color: rgba(255, 255, 255, 1);
  color: rgba(83, 75, 66, 1);
}

.search-field {
  border: 0.2vw solid #E0E3EB;
  border-radius: 0vw;
  width: 35vw;

  @media only screen and (max-width: 600px) {
    border: 2px solid #E0E3EB;
    border-radius: 0vw;
    width: 70vw;
  }
}

.icon {
  @media only screen and (max-width: 600px) {
    font-size: 4svb;
  }
}

.button {
  padding: 0;
}

.search {
  @media only screen and (max-width: 600px) {
    font-size: 2svb;
  }


}

.btn {

  text-transform: none !important;
  border-radius: 0vw;
  background-color: #2b7059;
  font-family: Lexend;
  font-weight: 600;
  text-align: center;
  color: #FFFFFF;
  padding: 1.5vw 0.5vw 2.8vw 1vw;

  @media only screen and (max-width: 600px) {

    border-radius: 0vw;
    font-size: 2svb;
    padding: 3svb 0 5.5svb 0;
  }

}

@media only screen and (max-width: 768px) {
  h1.title1 {
    font-family: Merriweather;
    font-size: 6svb;
    font-weight: 300;

    text-align: left;
    color: rgba(18, 18, 18, 1);
  }

  .title2 {
    font-family: Varta;
    font-size: 3svb;
    font-weight: 400;
    letter-spacing: 0px;
    text-align: left;
    color: rgba(112, 100, 88, 0.9);
  }

  .title3 {
    text-transform: none !important;
    color: #2b7059;
    font-family: Karla;
    font-size: 2.2svb;
    font-weight: 700;
    letter-spacing: 0.30000001192092896px;
    text-align: left;
  }

  .custom-text-field {
    background-color: rgba(255, 255, 255, 1);
    color: rgba(83, 75, 66, 1);
  }

  .subscribe {
    display: inline;
  }

  .btn {
    width: 200px;
  }
}

@media only screen and (min-width: 768px) {
  .custom-text-field {
    background-color: rgba(255, 255, 255, 1);
    color: rgba(83, 75, 66, 1);
    font-size: 5vw;
    height: 50px;

  }

  .title1 {
    font-family: Merriweather;
    font-size: 2.5vw;
    font-weight: 300;
    color: #2b7059;
  }

  .title2 {
    font-family: Varta;
    font-size: 1.2vw;
    font-weight: 400;
    text-align: left;
    color: rgba(112, 100, 88, 0.9);
  }

  .title3 {
    color: rgb(43, 112, 89);
    font-family: Karla;
    font-size: 1vw;
    font-weight: 700;
    letter-spacing: 0.3px;
    text-align: left;
  }

  .subscribe {
    display: flex;
    margin-top: 60px;
  }
}
</style>
