<template>
  <div  class="sliders">
    <v-row>
      <v-col>
        <v-row v-if="!isMobile">
          <swiper
            ref="swiperRef"
            :slides-per-view="3"
            :space-between="30"
            :navigation="navigation"
            :modules="modules"
            class="mySwiper"
          >
            <swiper-slide v-for="(slide, index) in slides" :key="index">
              <div>
                <img :src="slide.img" alt="Slide Image" />
              </div>
            </swiper-slide>
          </swiper>

          <v-col>
            <v-row>
              <!-- Left column -->
              <v-col md="3">
                <h3 class="title">Inspirations</h3>
              </v-col>
              <v-col md="5">
                <p class="description">
                  Our experts are keen to stay on top of trends in order to
                  offer you new inspirations for your interior and exterior
                  every day. Remember that to inspire you we have to inspire
                  ourselves and we want to share that with you.
                </p>
              </v-col>

              <!-- Right column - Subscription form -->
              <v-col md="2">
                <v-col class="d-flex">
                  <v-col>
                    <v-btn
                      size="2vw"
                      class="swiper-button swiper-button-prev"
                      density="compact"
                      icon="mdi-chevron-left "
                      variant="outlined"
                      color=" rgb(43, 112, 89)"
                      @click="prevSlide"
                    ></v-btn>
                  </v-col>
                  <v-col>
                    <v-btn
                      size="2vw"
                      class="swiper-button swiper-button-next"
                      density="compact"
                      icon="mdi-chevron-right  "
                      variant="outlined"
                      color=" rgb(43, 112, 89)"
                      @click=" nextSlide"
                    ></v-btn>
                  </v-col>
                </v-col>

                <v-btn
                  :disabled="currentPage === totalSlides - 1"
                  variant="plain"
                  class="swiper-button button"
                >
                  {{ (currentPage + 1).toString().padStart(2, "0") }} /
                  {{ totalSlides.toString().padStart(2, "0") }}
                </v-btn>
              </v-col>
            </v-row>
          </v-col>
        </v-row>

        <v-row v-else>
          <!-- Layout for mobile devices -->
          <v-col md="12 " class="inspo">
            <h3 class="title2">Inspirations</h3>
            <p class="description2">
              Our experts are keen to stay on top of trends in order to offer
              <br />
              you new inspirations for your interior and exterior every day.
              Remember that to inspire you we have to inspire ourselves and we
              want to share that with you.
            </p>
          </v-col>
        </v-row>
      </v-col>
    </v-row>

    <v-row v-if="isMobile">
      <v-col class="d-flex flex-column justify-center">
        <!-- First Row -->
        <v-row>
          <v-col
            v-for="(slide, index) in slides.slice(0, 2)"
            :key="index"
            class="custom-grid-item"
          >
            <img :src="slide.img" alt="Grid Image" height="200" width="150" />
            <h3>Inspirations</h3>
          </v-col>
        </v-row>

        <!-- Second Row -->
        <v-row>
          <v-col
            v-for="(slide, index) in slides.slice(2, 4)"
            :key="index"
            class="custom-grid-item"
          >
            <img :src="slide.img" alt="Grid Image" height="200" width="150" />
            <h3>Inspirations</h3>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import { ref, nextTick, computed } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination, Navigation } from "swiper/modules";
import "swiper/css";
import "swiper/css/pagination";
import "swiper/css/navigation";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const modules = [Pagination, Navigation];
    const swiperRef = ref(null);
    const isMobile = computed(() => window.innerWidth < 600); // Adjust the breakpoint as needed
    const slides = [
      {
        img: require("@/assets/1.png"),
      },
      {
        img: require("@/assets/2.png"),
      },
      {
        img: require("@/assets/3.jpg"),
      },
      {
        img: require("@/assets/1.png"),
      },
      {
        img: require("@/assets/2.png"),
      },
    ];

    let prevSlide = () => {
      nextTick(() => {
        if (swiperRef.value && swiperRef.value.swiper) {
          swiperRef.value.swiper.slidePrev();
        }
      });
    };

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
      nextEl: ".swiper-button-next",
      prevEl: ".swiper-button-prev",
    };

    return {
      modules,
      swiperRef,
      prevSlide,
      nextSlide,
      navigation,
      slides,
      currentPage,
      totalSlides,
      isMobile,
    };
  },
};
</script>

<style scoped>
@media only screen and (min-width: 768px) {
  .swiper-button {
    
    color: rgb(54, 97, 83);
    font-family: Karla;
    font-size: 1vw;
    font-weight: 700;
    letter-spacing: 0.30000001192092896px;
    
  }
  .swiper-button-next{
    margin-left: -70%;
  }
.swiper-button-prev{
  margin-left: -30%;
}
.button{
  bottom: 15%;
  margin-left: 10%;
}
  .swiper {
    width: 100%;
    height: 100%;
  }

  .swiper-slide {
    text-align: start;
    font-size: 1.2wv;
    background: #fff;
    justify-content: left;
    align-items: left;
    overflow: visible;
  }

  .swiper-slide img {
    width: 100%;
    height: 80vh;
  }
  h3.title {
    font-family: Merriweather;
    font-size: 3vw;
    font-weight: 300;
    line-height: 40px;
    letter-spacing: -0.30000001192092896px;
    text-align: left;
    color: rgb(25, 92, 70);
    margin-top: 2vh;
    margin-left: -3%;
  }
  p.description {
    margin-top: 2vh;
    height: 100%;
    width: 85%;
    font-family: Varta;
    font-size: 1.5vw;
    font-weight: 400;
    line-height: 3vh;
    text-align: left;

    color: rgba(112, 100, 88, 1);
  }
}
@media only screen and (max-width: 768px) {
  h3.title2 {
    color: rgba(83, 75, 66, 1);
    font-family: Merriweather;
    font-size: 35px;
    font-weight: 400;
    line-height: 40px;
    letter-spacing: -0.30000001192092896px;
    text-align: left;
  }
  p.description2 {
    font-family: varta;
    font-size: 18px;
    font-weight: 400;
    line-height: 25px;
    letter-spacing: 0px;
    text-align: left;
    padding-top: 20px;
    color: rgba(112, 100, 88, 1);
  }
}
</style>
