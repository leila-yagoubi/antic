<template>
  <v-footer class="d-flex flex-column footer ">
    <!-- Content Rows -->
    <div class="footer-content">
      <!-- First Row -->
      <div class="row">
        <div class="footer-section">
          <h4 class="title">antic</h4>
        </div>
        <div class="footer-section">
          <h1 class="column">Products</h1>
          <p class="text-caption">Furniture</p><br />
          <p class="text-caption">Decoration</p><br />
          <p class="text-caption">Storage</p><br />
          <p class="text-caption">Baby and child</p><br />
          <p class="text-caption">Connected home</p><br />
        </div>
        <div class="footer-section">
          <h4 class="column">Rooms</h4>
          <p class="text-caption">Living room</p><br />
          <p class="text-caption">Dining room</p><br />
          <p class="text-caption">Cooked</p><br />
          <p class="text-caption">Bedroom</p><br />
          <p class="text-caption">Bathroom</p><br />
          <p class="text-caption">Office</p><br />
          <p class="text-caption">Laundry</p><br />
        </div>
        <div class="footer-section">
          <h4 class="column">Services</h4>
          <p class="text-caption">Click and collect</p><br />
          <p class="text-caption">Conception</p><br />
          <p class="text-caption">Installation</p><br />
          <p class="text-caption">Advices</p><br />
          <p class="text-caption">Gift card</p><br />
        </div>
        <div class="footer-section">
          <h4 class="column">About</h4>
          <p class="text-caption">Our story</p><br />
          <p class="text-caption">Our stores</p><br />
          <p class="text-caption">Our partners</p><br />
        </div>
        <div class="footer-section"  >
          <h1 class="column1 ">We respect our planet</h1>
          <v-img src="@/assets/lastPicture.png"  width="100%"/>
          <p class="text-caption">We’re taking positive steps to reduce our impact on the planet. For us, that means retailing responsibly.</p>
          <v-btn append-icon="mdi-chevron-right" variant="text" class="btn mr-14">
            Learn more
          </v-btn>
        </div>
      </div>

      <!-- Social Icons Row -->
      <div class="footer-section  bgTop text-center  " color="rgba(112, 100, 88, 0.9)">
        <v-icon class="mr-1">mdi mdi-facebook</v-icon>
        <v-icon class="mr-1">mdi mdi-twitter</v-icon>
        <v-icon class="mr-1">mdi mdi-instagram</v-icon>
        <v-icon class="mr-1">mdi mdi-linkedin</v-icon>
      </div>

      <!-- Copyright Row -->
      <div class="footer-section   ">
        <div class="row" >
          <!-- Left Section -->
          
          <div class="footer-section ">
            <v-icon class="copyright ">mdi mdi-copyright</v-icon>
            <strong>Copyright {{ new Date().getFullYear() }} Agence Dnd</strong>
            
          </div>
          <v-spacer></v-spacer>
          <div class="footer-section text-right">
          <!-- Right Sections -->
           <v-row class="pl-15 pt-5">
           
            <h4 class="pr-2 privacy">Privacy policy</h4> 
             <h4  class="pr-2 pl-2 privacy">Term of service</h4>
             <h4 class="pl-2 privacy">Language</h4>
          </v-row>
       
        </div>
         
        </div>
      </div>
    </div>
  </v-footer>
</template>

<script>
export default {}
</script>

<style scoped>
/* Add your styles here */
.footer {
  background-color: rgba(243, 238, 232, 1);
  padding: 5% 9% 5% 9%;
}

.footer-content {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.row {
  display: flex;
  gap: 1.5vw;
}

.footer-section {
 color: rgba(112, 100, 88, 0.7);
 flex: 1;
  flex-direction: column;
  gap: 2vw;
  font-size: 1.2vw;
}
.text-caption {
font-size: 1px;
line-height: 2.5vh;
color: rgba(112, 100, 88, 1);
}
.title{
  font-family: Merriweather;
font-size: 3vw;
line-height: 25px;
letter-spacing: 2px;
text-align: left;
color: rgb(43, 112, 89);
}


.column{
  font-family: Varta;
font-size: 1.8vw;

font-weight: 800;
line-height: 8vh;
letter-spacing: -0.20000000298023224px;
text-align: left;
color: rgba(83, 75, 66, 1);
}
.column1{
  font-family: Varta;
font-size: 1.8vw;
line-height: 4vh;
letter-spacing: -0.20000000298023224px;
text-align: left;
color: rgba(83, 75, 66, 1);
}


.btn{
  font-family: Karla;
font-size: 1vw;
font-weight: 700;
line-height: 25px;
letter-spacing: 0.30000001192092896px;
text-align: left;
justify-content: left;
color: rgba(160, 96, 86, 1);
}

.privacy{
font-family: Varta;
font-size: 1vw;
font-weight: 500;
text-align: left;
color: rgba(112, 100, 88, 0.7);
}
@media screen and (max-width: 600px) {
  .footer {
    padding: 30px 10px 44px 10px; 
  }
 
  .row {
    flex-direction: column;
  }

.title {
    align-items: stretch;
    align-self: center; 
    text-align: center;    
  } 
.footer-section{
  gap:24px;
}
.text-caption{
  font-size: 1vw;
}  .footer-content{
    padding: 25px;
  }
}
</style>
