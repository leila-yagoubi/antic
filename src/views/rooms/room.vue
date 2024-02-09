<template>
    <div class="room">
   <v-col>
     <h2 class="title ">Find your room</h2>
      
       <Slide/> 
   </v-col>
       
    
     
    </div>
</template>

<script>
import Slide from './slide.vue';
export default {
components:{
  Slide
}
}
</script>

<style>

</style>
<style scoped>
.room{
  background:rgba(243, 238, 232, 1);
}
@media only screen and (min-width: 768px) {
  .room{
    padding: 4% 7% 4% 7%;
  }
.title{

  font-family: Merriweather;
font-size: 4vw;
line-height: 15vh; 
font-weight: 300;
text-align: left;
color: rgb(88, 112, 106);
}}

@media only screen and (max-width: 768px) {

  .title{
  font-family: Merriweather;
font-size: 5svb;
font-weight: 300;

letter-spacing: -0.6000000238418579px;
text-align: left;
color: rgb(90, 112, 88);

}
}
</style>