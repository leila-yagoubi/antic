<template>
  <v-footer class="d-flex flex-column footer">
    <v-row>
      <!-- First Row -->
      <v-col cols="12" md="12" >
        <v-row>
          <v-col cols="12" md="2">
            <h4 class="mt-2 title">antic</h4>
            
          </v-col>
          <v-col cols="12" md="2">
            <h4 class="mt-2 column">Products</h4>
            <span class="text-caption">Furniture</span><br />
            <span class="text-caption">Decoration</span><br />
            <span class="text-caption">Storage</span><br />
            <span class="text-caption">Baby and child</span><br />
            <span class="text-caption">Connected home</span><br />
          </v-col>
          <v-col cols="12" md="2">
            <h4 class="mt-2 column">Rooms</h4>
            <span class="text-caption">Living room</span><br />
            <span class="text-caption">Dining room</span><br />
            <span class="text-caption">Cooked</span><br />
            <span class="text-caption">Bedroom</span><br />
            <span class="text-caption">Bathroom</span><br />
            <span class="text-caption">Office</span><br />
            <span class="text-caption">Laundry</span><br />
          </v-col>
          <v-col cols="12" md="2">
            <h4 class="mt-2 column">Services</h4>
            <span class="text-caption">Click and collect</span><br />
            <span class="text-caption">Conception</span><br />
            <span class="text-caption">Installation</span><br />
            <span class="text-caption">Advices</span><br />
            <span class="text-caption">Gift card</span><br />

          </v-col>
          <v-col cols="12" md="2">
            <h4 class="mt-2 column">About</h4>
            <span class="text-caption">Our story</span><br />
            <span class="text-caption">Our stores</span><br />
            <span class="text-caption">Our partners</span><br />
          </v-col>
          <v-col cols="12" md="2">
            <h4 class="mt-2 column">We respect our planet</h4>
            <v-img src='@/assets/lastPicture.png'  height="100" width="150"/>
            <p class="text-caption">We’re taking positive steps to reduce our impact on the planet. For us, that means retailing responsibly.</p>
            <v-btn append-icon="mdi-chevron-right "  variant="plain" class="title3 mr-10"  >
                        Learn more
                        </v-btn>
                       
          </v-col>
        </v-row>
      </v-col>

     <v-col class="px-4 py-8 bgTop text-center w-100 copyright">
         <v-icon class="mr-1">mdi mdi-facebook</v-icon>
          <v-icon class="mr-1">mdi mdi-twitter</v-icon>
          <v-icon class="mr-1">mdi mdi-instagram</v-icon>
          <v-icon class="mr-1">mdi mdi-linkedin</v-icon>
      </v-col>
    </v-row>

    <!-- Copyright Row -->
    <div class="px-14 py-15 bgTop text-center w-100 text-black">
     
     <v-row>
      <v-col md="4 copyright">    
       <v-icon class="copyright" >mdi mdi-copyright</v-icon>
      <strong >Copyright {{ new Date().getFullYear() }} Agence Dnd</strong>
</v-col>
      <v-col md="2 copyright">
        <h4 >Privacy policy</h4>
      </v-col>
      <v-col md="2 copyright">
        <h4 >Term of service</h4>
      </v-col>
      <v-col md="2 copyright" >
        <h4 >Language</h4>
      </v-col>
     </v-row>
     
    </div>
  </v-footer>
</template>

<script>
export default {
  // Your script code here
}
</script>

<style scoped>
.v-footer {
  background-color: rgba(243, 238, 232, 1);
  
  position: relative;
  
  width: 100%;
  padding-top: 50px;
  padding-right: 100px;
  padding-left: 100px;
 
}

.copyright{
  font-family: Varta;
font-size: 18px;
font-weight: 400;
line-height: 25px;
letter-spacing: 0px;
text-align: left;

color: rgba(112, 100, 88, 0.7);
}
.title{
 
  font-family: Merriweather;
font-size: 34px;
font-weight: 700;
line-height: 25px;
letter-spacing: 2px;
text-align: left;
color: rgba(83, 75, 66, 1);
}
h4.column{

  font-family: Varta;
font-size: 25px;
font-weight: 600;
line-height: 30px;
letter-spacing: -0.20000000298023224px;
text-align: left;
color: rgba(83, 75, 66, 1);
}
.text-caption{
 
  
  font-family: Varta;
font-size: 18px;
font-weight: 400;
line-height: 25px;
letter-spacing: 0px;
text-align: left;
color: rgba(112, 100, 88, 1);
width: 235px;
}
.title3{
  color: rgba(160, 96, 86, 1);
  font-family: Karla;
font-size: 17px;
font-weight: 700;
line-height: 25px;
letter-spacing: 0.30000001192092896px;
text-align: left;

}
</style>
