<template>
    

    <div class="inspiration">
    
    <newsletter/>
    <Slider/>
  
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

@media only screen and (min-width: 768px){
    .inspiration{
        padding: 70px 50px 64px 50px;
    }
}
@media only screen and (max-width: 768px){}
.inspiration{
  
    background-color:rgba(255, 255, 255, 1);
}
</style>