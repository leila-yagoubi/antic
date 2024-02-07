<template>
  <div fluid class="newsletter">
    <v-row>
      <v-col md="6">
        <h1 class="title1">Be aware of the latest trends</h1>
        <p class="title2">
          Stay informed of new trends, but also of our various offers.
        </p>
        <v-btn class="mt-4" variant="text">
          <h6 class="title3">Find out more</h6>
          <v-icon
            end
            icon="mdi-chevron-right"
            size="1.5vw"
            color="var(--Terracotta, #A06056)"
          ></v-icon>
        </v-btn>
      </v-col>

      <!-- Right column - Subscription form -->
      <v-col md="5">
        <div class="subscribe">
        
          <v-text-field
        

            placeholder="Enter your email here"
            elevation="0"
            class="custom-text-field"
          ></v-text-field>
          <v-btn
            class="btn text-none"
            color="rgba(83, 75, 66, 1)"
           
            variant="flat"
            rounded="0"
            elevation="0"
            @click="subscribe"
          >
            Subscribe Now
          </v-btn>
        </div>
      </v-col>
      <v-col cols="1">

      </v-col>
    </v-row>
  </div>
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
.newslatter {
  background-color: rgba(255, 255, 255, 1);
}

.custom-text-field {
  min-height: auto !important;
  background-color: rgba(255, 255, 255, 1);
  color: rgba(83, 75, 66, 1);
}

@media only screen and (max-width: 768px) {
  h1.title1 {
    font-family: Merriweather;
    font-size: 30px;
    font-weight: 300;
    line-height: 40px;
    height: 80px;
    width: 150;
    text-align: center;
    color: rgba(18, 18, 18, 1);
  }

  .title2 {
    font-family: Varta;
    font-size: 18px;
    font-weight: 400;
    line-height: 25px;
    letter-spacing: 0px;
    text-align: left;
    width: 290px;
    height: 50px;
    color: rgba(112, 100, 88, 0.9);
  }

  .title3 {
    color: rgba(160, 96, 86, 1);
    font-family: Karla;
    font-size: 17px;
    font-weight: 700;
    line-height: 25px;
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
    width: 300px;
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
