<template>
  <div>
    <!-- Desktop view -->
    <v-row v-if="!isMobile">

      <v-card class="mx-auto d-flex" width="100% " height="100%" color="rgba(243, 238, 232, 1)" elevation="0">
        <v-col cols="12" md="2">
          <p class="description">Dining room, bedroom, bathroom or office. Find what you need</p>
        </v-col>
        <v-col cols="10">
          <swiper ref="swiperRef" :slides-per-view="2" :space-between="40" :navigation="navigation" :modules="modules"
            class="mySwiper">
            <swiper-slide v-for="(slide, index) in slides" :key="index">
              <div>
                <img height="300" class="images" :src="slide.img" :contain="true">
                <div class="overlay">
                  <h2 class="title five">{{ slide.title }}</h2>
                  <p class="arrival">{{ slide.description }}</p>
                </div>
              </div>
            </swiper-slide>
          </swiper>
        </v-col>
      </v-card>
    </v-row>
    <!-- Mobile view -->
    <!-- Mobile view -->
    <div v-else>
      <v-col cols="12" md="2">
        <p class="description">Dining room, bedroom, bathroom or office. Find what you need</p>
      </v-col>
      <swiper ref="swiperRef" :navigation="navigation" :modules="modules" class="mySwiper">
        <swiper-slide v-for="(slide, index) in slides" :key="index">
          <div class="mobile-slide w-full">
            <img height="300" :src="slide.img" class="left-image " :contain="true">
            <div class="text-container">
              <h2 class="title five">{{ slide.title }}</h2>
              <p class="arrival">{{ slide.description }}</p>
            </div>
          </div>
        </swiper-slide>
      </swiper>
    </div>
    <!-- Pagination and navigation buttons -->
    <v-row :class="{ 'flex-row': isMobile, 'flex-row': !isMobile }">

      <v-col cols="8" md="1">
        <v-btn :disabled="currentPage === totalSlides - 1" variant="text" class="swiper-button ">
          {{ (currentPage + 1).toString().padStart(2, '0') }} / {{ totalSlides.toString().padStart(2, '0') }}
        </v-btn>
      </v-col>
      <v-col cols="4" md="2">
        <v-btn append-icon="mdi-chevron-right" variant="text" class="swiper-button-next ml-8" @click="nextSlide">
          next
        </v-btn>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import { ref, nextTick, computed } from 'vue';
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Pagination, Navigation } from 'swiper/modules';
import 'swiper/css';
import 'swiper/css/pagination';
import 'swiper/css/navigation';
import { useDisplay } from 'vuetify';

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const { xs, smAndDown } = useDisplay()
    const modules = [Pagination, Navigation];
    const swiperRef = ref(null);
    const isMobile = computed(() => window.innerWidth < 600); // Adjust the breakpoint as needed
    const slides = [
      {
        title: 'Bedroom ',
        img: require('@/assets/7.jpg'),
        description: "New arrivals",

      },
      {
        title: 'Living room ',
        img: require('@/assets/salon.jpg'),
        description: "New arrivals",

      },
      {
        title: 'Living room 1',
        img: require('@/assets/6.jpg'),
        description: "New arrivals",

      },
      {
        title: 'Batheroom',
        img: require('@/assets/8.jpg'),
        description: "New arrivals",

      },
    ];

    let currentPage = ref(0);
    let totalSlides = ref(slides.length);

    let nextSlide = () => {
      nextTick(() => {
        if (swiperRef.value && swiperRef.value.swiper) {
          swiperRef.value.swiper.slideNext();
          currentPage.value = swiperRef.value.swiper.realIndex;
        }
      });
    };

    const navigation = {
      nextEl: '.swiper-button-next',
    };

    return { modules, swiperRef, nextSlide, currentPage, totalSlides, navigation, slides, xs, smAndDown, isMobile };
  },
};
</script>


<style scoped>
@media only screen and (min-width: 768px) {

  .five {
    position: absolute;
    top: 50%;
    left: 5%;
    width: 100%;
    height: auto;
    transform: translate(55%, -55%);
  }

  .title {
    font-family: Merriweather;
    font-size: 3.2vw;
    font-weight: 500;
    line-height: 6vh;
    text-align: left;
    color: #2b7059;
    width: 60%;
  }

  .arrival {
    position: absolute;
    font-size: 1.8vw;
    left: 61%;
    top: 0%;
    white-space: normal;
    font-family: Varta;
    font-weight: 400;
    text-align: right;
    color: rgba(112, 100, 88, 0.9);
  }

  .description {
    font-size: 1.5vw;
    font-family: Varta;
    font-weight: 400;
    line-height: 3.5vh;
    text-align: left;
    color: rgba(112, 100, 88, 0.9);
    width: 100%;
  }

  .swiper-button-next {
    color: #2b7059;
    font-family: Karla;
    font-size: 1.8vw;
    font-weight: 700;
    letter-spacing: 0.30000001192092896px;
    text-align: left;
    padding-left: 70%;
  }

  .swiper-slide img {
    width: 60%;
    height: 60vh;
  }

  .swiper-button {
    color: rgb(170, 162, 160);
    font-family: Karla;
    font-size: 1vw;
    margin-top: 20%;
  }
}

@media only screen and (max-width: 768px) {

  .description {
    font-family: Varta;
    font-size: 3svb;
    font-weight: 400;
    line-height: 25px;
    letter-spacing: 0px;
    text-align: left;
    color: #818181;
    margin-left: -4%;
  }

  .mobile-slide {
    display: flex;
    flex-direction: row;
    width: 100%;
  }

  .left-image {
    width: 60%;
    height: 50vh;
  }

  .text-container {
    width: 50%;
    flex-direction: column;
  }

  .title {
    font-family: Merriweather;
    font-size: 4.2svb;
    letter-spacing: -0.6000000238418579px;
    text-align: left;
    color: #2b7059;
    margin-bottom: 10px;
    /* Adjust margin as needed */
  }

  .arrival {
    margin: 0;
    font-size: 3svb;
    white-space: normal;
    font-family: Varta;
    font-weight: 400;
    text-align: right;
    color: rgba(112, 100, 88, 0.9);
    padding-right: 20px;
  }

  .five {
    position: absolute;
    top: 50%;
    left: 40%;
    width: 50%;
    height: auto;
    transform: translate(10%, -55%);
  }

  .button {
    flex-direction: row;
  }

  .swiper-button-next {

    color: #2b7059;
    font-family: Karla;
    font-size: 3svb;
    font-weight: 700;
    line-height: 25px;
    letter-spacing: 0.30000001192092896px;


  }


}
</style>