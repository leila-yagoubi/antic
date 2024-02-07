<template>
  <div class=" hero">

    <!-- Main content -->
    <v-col cols="12" md="6" xs="12" sm="12">

      <!-- Colored background div -->
      <div class="custumetitle">
        <v-card-title>
          <h2 class="title1  ">HOME DESIGN</h2>
        </v-card-title>
        <v-card-title>
          <h3 class="title2 ">Elegance for <br> Interiors & <br> Exteriors</h3>
        </v-card-title>
        <v-card-text>
          <h1 class="title3 ">We provide everyone with modern, trendy, quality furniture</h1>
        </v-card-text>

        <v-col>
          <v-btn class="button" icon="mdi-chevron-down " variant="outlined " size="3.2vw"></v-btn>
        </v-col>

      </div>
    </v-col>

  </div>
</template>

<script>
export default {
  components: {}
}
</script>

<style scoped>
.hero {
  background: url('@/assets/pic1.jpg') no-repeat right;
  background-size: 50%;
  background-color: rgba(243, 238, 232, 1);
  height: 100%;
  width: 100%;
}

@media only screen and (max-width: 768px) {
  .hero {
  
    background: linear-gradient(rgba(81, 156, 131, 0.089), rgb(17, 87, 62)),  url('@/assets/pic1.jpg') no-repeat center center ;

    background-size: cover;
    padding: 30vh 5% 0% 5%;
    height: 100vh;
    width: 100%;
  }
  .card {
    padding: 0px 0px 0px 0px;
    gap: 28;
    display: flex;
    flex-direction: column;
  }
  .button {
    color: #2b7059;
    margin-left: 50%;
    margin-bottom: 100px;
    width: 5vw;
    height: 5vw;
  }

  h2.title1 {
    height: 20px;
    font-family: Varta;
    font-size: 4svb;
    font-weight: 700;
    line-height: 20px;
    letter-spacing: 1px;
    text-align: center;
    color: rgb(255, 255, 255);
  }

  h3.title2 {
    width: 100%;
    font-family: Merriweather;
    font-size: 7svb;
    font-weight: 600;
    line-height: 9.5vh;
    letter-spacing: -0.30000001192092896px;
    text-align: center;
    color: rgba(255, 255, 255, 1);
  }

  h1.title3 {
    width: 100%;
    font-family: Varta;
    font-size: 4.2vw;
    font-weight: 400;
    line-height: 5vh;
    text-align: center;
    color: rgba(247, 248, 249, 1);
  }
}

@media only screen and (min-width: 768px) {
  .hero {
    height: 100vh;
    padding: 0% 0% 0% 5%;
  }

  .custumetitle {
    padding: 20% 0% 0% 0%;
  }

  h2.title1 {
    width: 420px;
    font-size: 2vw;
    margin-bottom: 20px;
    color: rgb(43, 112, 89);
    font-family: Varta;
    font-weight: 700;


  }

  h3.title2 {
    font-family: Merriweather;
    font-size: 6vw;
    font-weight: 300;
    line-height: 13vh;
    letter-spacing: -0.4000000059604645px;
    text-align: left;
    color: #2b7059;
  }

  h1.title3 {
    width: 65%;
    color: #706458E5;
    font-family: Varta;
    font-size: 1.8vw;
    font-weight: 300;
    line-height: 3.8vh;
    letter-spacing: 0px;
    text-align: left;
  }

  .button {
    color: #195a44;
    margin-left: 1.5%;

  }
}
</style>
