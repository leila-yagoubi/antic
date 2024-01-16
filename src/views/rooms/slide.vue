<template>
  <v-container class="slideRoom">
    <!-- Desktop view -->
    <v-row v-if="!isMobile">
      <v-card class="mx-auto d-flex" width="100% " height="100%" color="rgba(243, 238, 232, 1)" elevation="0">
    <v-col cols="1">
      
      <p class="description">Dining room, bedroom, bathroom or office. Find what you need</p>
      
    </v-col>
    <v-col cols="10">
      <swiper ref="swiperRef" :slides-per-view="2" :space-between="40" :navigation="navigation" :modules="modules" class="mySwiper">
                 <swiper-slide v-for="(slide, index) in slides" :key="index">               
                  
            <v-img   height="300"  :src="slide.img">
               <div class="overlay">
                <h2 class="title five">{{ slide.title }}</h2>
                <p class="arrival">{{ slide.description }}</p>
              </div>
            </v-img>
           
          </swiper-slide>
        </swiper>
    </v-col>
    </v-card>
  </v-row>
   

<!-- Mobile view -->
<!-- Mobile view -->
<div v-else>
      <swiper ref="swiperRef" :navigation="navigation" :modules="modules" class="mySwiper">
        <swiper-slide v-for="(slide, index) in slides" :key="index">
          <div class="mobile-slide">
            <v-img :src="slide.img" class="left-image"></v-img>
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
      <v-col cols="2">
        <v-btn :disabled="currentPage === totalSlides - 1" variant="text" class="swiper-button-next">
          {{ (currentPage + 1).toString().padStart(2, '0') }} / {{ totalSlides.toString().padStart(2, '0') }}
        </v-btn>
      </v-col>
      <v-col cols="2" >
        <v-btn append-icon="mdi-chevron-right" variant="text" class="swiper-button-next ml-10" @click="nextSlide">
          next
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import { ref, nextTick , computed} from 'vue';
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
        img: require('@/assets/4.png'),
        description: "New arrivals",
       
      },
      {
        title: 'Living room ',
        img: require('@/assets/5.png'),
        description: "New arrivals",
       
      },
      {
        title: 'Living room 1',
        img: require('@/assets/4.png'),
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

    return { modules, swiperRef, nextSlide, currentPage, totalSlides, navigation, slides, xs, smAndDown , isMobile};
  },
};
</script>


<style scoped>

@media only screen and (min-width: 768px) {
.slideRoom{
  padding: 70px 0px 64px 0px; 
}
.five {
  position: absolute;
  top: 50%;
  left: 25%;
  width: 100%;
  height: auto;
  transform: translate(55%, -55%);
}

.title {
  font-family: Merriweather;
  font-size: 40px;
  font-weight: 400;
  line-height: 60px;
  letter-spacing: -0.6000000238418579px;
  text-align: center;
  color: rgba(160, 96, 86, 1);
  width: 200px;
}
.arrival{
  font-size: 18px;
  white-space: normal;
  font-family: Varta;
  font-weight: 400;
  text-align: right;
  color: rgba(112, 100, 88, 0.9);
}
.description {
  font-size: 18px;
  font-family: Varta;
  font-weight: 400;
  line-height: 25px;
  text-align: left;
  color: rgba(112, 100, 88, 0.9);
  width: 150px;
}

.swiper-button-next {
 color: rgba(160, 96, 86, 1);
 font-family: Karla;
font-size: 20px;
font-weight: 700;
line-height: 25px;
letter-spacing: 0.30000001192092896px;
text-align: left;
padding-bottom: 20px;
margin-right: 20px;
}


}
@media only screen and (max-width: 768px){

  .description {
margin-bottom: 20px;
font-family: Varta;
font-size: 18px;
font-weight: 400;
line-height: 25px;
letter-spacing: 0px;
text-align: left;
}
.mobile-slide {
    display: flex;
    flex-direction: row;
    width: 100%;
  }

  .left-image {
    width: 50%;
  }

  .text-container {
    width: 50%;  
    flex-direction: column;   
  }

  .title {
    font-family: Merriweather;
    font-size: 20px;
    letter-spacing: -0.6000000238418579px;
    text-align: left;
    color: rgba(160, 96, 86, 1);
    margin-bottom: 10px; /* Adjust margin as needed */
  }

  .arrival {
    margin: 0;
    font-size: 18px;
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
  left: 25%;
  width: 50%;
  height: auto;
  transform: translate(10%, -55%);
}

.button{
  flex-direction: row; 

}
.swiper-button-next {
  
 color: rgba(160, 96, 86, 1);
 font-family: Karla;
font-size: 20px;
font-weight: 700;
line-height: 25px;
letter-spacing: 0.30000001192092896px;

padding-top: 20px;

}


}
</style>