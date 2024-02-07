<template>
  <div class="services">
   
      <v-col cols="12" md="12" xs="12" sm="12">

        <v-row>

          <!-- Left column -->
          <v-col cols="12" md="6">
            <v-card-title>
              <h3 class="title">We stay by your <br>side to design <br>your projects</h3>
            </v-card-title>
          
              <v-btn
        class="mt-4 "
        variant="text"
      >
      <h6 class="title2">Find out more</h6>
        <v-icon
          end
          icon="mdi-chevron-right"
          size="1.5vw"
          color="var(--Terracotta, #A06056)"
        ></v-icon>
      </v-btn>
              
    
          </v-col>

          <!-- Right columns -->
          <v-col cols="12" md="3" sm="5">
            <v-card class="cards">
              <v-card-text >
                <h3 class="subtitle">Our Advices</h3>
                <p class="text">  What if you took advantage of this rather special period to rethink your interior? You spend more time at
                home so you might as well feel good there.</p>
              </v-card-text>
            </v-card>

            <v-card class="cards">
              <v-card-text >
                <h3 class="subtitle">Conception Service</h3>
                <p class="text">  Personalized service with an expert advisor for your interior and exterior decoration or layout projects.</p>
              </v-card-text>
            </v-card>
          </v-col>

          <v-col cols="12" md="3" sm="5">
            <v-card class="cards">
              <v-card-text >
                <h3 class="subtitle">Click and Collect</h3>
              <p class="text">  Adapted and contactless. Free from € 200 of purchases in stores offering the service.</p>
              </v-card-text>
            </v-card>

            <v-card class="cards">
              <v-card-text >
                <h3 class="subtitle">Installation Service</h3>
              <p class="text">  Our furniture packaged in flat packs are designed for easy assembly. But you can call on our partner.</p>
              </v-card-text>
            </v-card>
          </v-col>

        </v-row>


      </v-col>
  </div>
</template>

<style scoped>
.services {
  background: #F3EEE8;

}
.cards {
  background-color: #F3EEE8;
  box-shadow: none;
}

@media only screen and (max-width: 768px) {

  .text {
    color: var(--Brown-Light, rgba(112, 100, 88, 0.90));
    font-family: Varta;
    font-size: 18px;
    font-weight: 400;

    letter-spacing: 0px;
    text-align: left;
  }

  .title {
    font-family: Merriweather;
    font-size: 35px;
    font-weight: 400;

    letter-spacing: -0.30000001192092896px;
    text-align: left;

    color: rgba(83, 75, 66, 1);
  }

  .title2 {
    color: var(--Terracotta, #A06056);
    font-family: Lato;
    font-size: 17px;
    font-weight: 900;
    line-height: 25px;
    letter-spacing: 0.30000001192092896px;
    text-align: left;


  }

  .subtitle {
    height: 30px;

    width: 311px;
    height: 30px;
    color: rgba(160, 96, 86, 1);
    font-family: Varta;
    font-size: 25px;
    font-weight: 600;
    line-height: 30px;
    letter-spacing: -0.20000000298023224px;
    text-align: left;

  }

}

@media screen and (min-width: 768px) {
  .services {
    padding: 4% 6% 4% 6%;
  }

  h3.title {
    color: rgba(112, 100, 88, 1);
    font-family: Merriweather;
    font-size: 4vw;
    font-weight: 300;
    line-height: 9vh; 
    letter-spacing: -0.6000000238418579px;
    text-align: left;
  }

  .title2 {
    color: var(--Terracotta, #2b7059);
    font-size: 1vw;
    margin-left: 20px;
    letter-spacing: 0.3px;
  }

  .cards{
    display: flex;
    font-family: Karla;
    height: 54%;
    
  }

  .subtitle {
    font-family: Varta;
    color: #2b7059;
    font-size: 1.6vw;
    line-height: 6vh;
    font-weight: 600;
    word-wrap: break-word;
  }

  .text {
    color: var(--Brown-Light, rgba(112, 100, 88, 0.90));
    font-family: Varta;
    font-size: 1.25vw;
    line-height: 3vh;
    text-align: left;
    width: 100%;
    height: 100%;
  }

  .title {
    font-family: Merriweather;
    font-size: 55px;
    font-weight: 300;
    line-height: 60px;
    letter-spacing: -0.6000000238418579px;
  }

}</style>
