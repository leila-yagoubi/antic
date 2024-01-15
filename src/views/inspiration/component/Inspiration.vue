<template>
    <div class="inspiration">

    
    <v-container >
    <newsletter/>
    <Slider/>

    </v-container>
    </div>
</template>

<script>
import newsletter from './Newslatter.vue'
import Slider from './Slider.vue'
export default{
    components:{
     newsletter,
     Slider,
    }
}
</script>

<style>
.inspiration{
    position: relative;
    background-color:rgba(255, 255, 255, 1);

   
}
</style>