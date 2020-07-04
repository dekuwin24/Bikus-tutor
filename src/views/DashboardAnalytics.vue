<!-- =========================================================================================
  File Name: DashboardAnalytics.vue
  Description: Dashboard Analytics
  ----------------------------------------------------------------------------------------
  Item Name: Vuexy - Vuejs, HTML & Laravel Admin Dashboard Template
  Author: Pixinvent
  Author URL: http://www.themeforest.net/user/pixinvent
========================================================================================== -->

<template >
  <div id="dashboard-analytics" class=" p-0 m-0 ">
    <vs-divider class="pb-1 mb-1 " color="gray"  icon="star"></vs-divider>


    <swiper :options="swiperOption" :dir="$vs.rtl ? 'rtl' : 'ltr'" :key="$vs.rtl" class="  w-full pb-0">

      <swiper-slide>
        <img class="responsive image" src="@/assets/images/pages/carousel/banner-64.jpg" alt="banner">
      </swiper-slide>

      <!-- <swiper-slide class="pb-0" > -->
        <!-- <div class="flex h-full pr-0 mr-0  flex-col "> -->

          <!-- <div class=" bg-primary text-white rounded px-4 py-2 m-2"> -->
            <!-- <div class=" text-center  ">
              <p class="text-3xl  h-full">BIENVENU À <br/> </p>
            </div> -->
            <!-- <div class="text-center w-1/3">
              <p class="text-3xl  h-full"> --oo-- <br/> </p>

            </div>

            <div class="text-center w-1/3">
              <p class="text-3xl  h-full"> <br/>  </p>
            </div> -->
          <!-- </div> -->
          <!-- <hr/> -->

          <!-- <div class=" flex  px-4 py-2 m-2"> -->
            <!-- <div class="w-1/2 container4 center text-center ">
              <strong class=" text-6xl text-center italic bikus">BIKUSTUTOR</strong>  <br/>
            </div> -->
            <!-- <div class="float-right w-1/2 pr-0 mr-0 h-full"> -->
              <!-- <img class="responsive w-full image  pr-0 mr-0 " src="@/assets/images/pages/carousel/banner-65.jpg" alt="banner"> -->
            <!-- </div> -->

          <!-- </div> -->
      <!-- </div> -->

      <!-- </swiper-slide> -->

      <!-- <swiper-slide>
        <img class="responsive image" src="@/assets/images/pages/carousel/banner-54.jpg" alt="banner">
      </swiper-slide>

      <swiper-slide class="">
        <img class="responsive w-full image  pr-0 mr-0 " src="@/assets/images/pages/carousel/banner-67.jpg" alt="banner">
      </swiper-slide> -->

      <!-- <swiper-slide>
        <img class="responsive image" src="@/assets/images/pages/carousel/banner-44.jpg" alt="banner">
      </swiper-slide>
      <swiper-slide>
        <img class="responsive image" src="@/assets/images/pages/carousel/banner-45.jpg" alt="banner">
      </swiper-slide> -->
      <!-- <swiper-slide>
        <img class="responsive" src="@/assets/images/pages/carousel/banner-2.jpg" alt="banner">
      </swiper-slide> -->
      <!-- <div class="swiper-pagination" slot="pagination"></div> -->
      <!-- <div class="swiper-button-prev" slot="button-prev"></div>
      <div class="swiper-button-next" slot="button-next"></div> -->
    </swiper>

    <!-- <div class="vx-row">
      <vx-card class="bg-white">
        <vs-divider class="p-0 m-0" color="gray"  icon="star"></vs-divider>

        <swiper :options="swiperOption" :dir="$vs.rtl ? 'rtl' : 'ltr'" :key="$vs.rtl" class=" rounded w-full pb-0">

          <swiper-slide>
            <img class="responsive image" src="@/assets/images/pages/carousel/banner-63.jpg" alt="banner">
          </swiper-slide>

          <swiper-slide class="pb-0" > -->
            <!-- <div class="flex h-full pr-0 mr-0  flex-col "> -->

              <!-- <div class=" bg-primary text-white rounded px-4 py-2 m-2"> -->
                <!-- <div class=" text-center  ">
                  <p class="text-3xl  h-full">BIENVENU À <br/> </p>
                </div> -->
                <!-- <div class="text-center w-1/3">
                  <p class="text-3xl  h-full"> --oo-- <br/> </p>

                </div>

                <div class="text-center w-1/3">
                  <p class="text-3xl  h-full"> <br/>  </p>
                </div> -->
              <!-- </div> -->
              <!-- <hr/> -->

              <!-- <div class=" flex  px-4 py-2 m-2"> -->
                <!-- <div class="w-1/2 container4 center text-center ">
                  <strong class=" text-6xl text-center italic bikus">BIKUSTUTOR</strong>  <br/>
                </div> -->
                <!-- <div class="float-right w-1/2 pr-0 mr-0 h-full"> -->
                  <!-- <img class="responsive w-full image  pr-0 mr-0 " src="@/assets/images/pages/carousel/banner-65.jpg" alt="banner"> -->
                <!-- </div> -->

              <!-- </div> -->
          <!-- </div> -->

          <!-- </swiper-slide>

          <swiper-slide>
            <img class="responsive image" src="@/assets/images/pages/carousel/banner-54.jpg" alt="banner">
          </swiper-slide>

          <swiper-slide class="">
            <img class="responsive w-full image  pr-0 mr-0 " src="@/assets/images/pages/carousel/banner-67.jpg" alt="banner">
          </swiper-slide> -->

          <!-- <swiper-slide>
            <img class="responsive image" src="@/assets/images/pages/carousel/banner-44.jpg" alt="banner">
          </swiper-slide>
          <swiper-slide>
            <img class="responsive image" src="@/assets/images/pages/carousel/banner-45.jpg" alt="banner">
          </swiper-slide> -->
          <!-- <swiper-slide>
            <img class="responsive" src="@/assets/images/pages/carousel/banner-2.jpg" alt="banner">
          </swiper-slide> -->
          <!-- <div class="swiper-pagination" slot="pagination"></div> -->
          <!-- <div class="swiper-button-prev" slot="button-prev"></div>
          <div class="swiper-button-next" slot="button-next"></div> -->
        <!-- </swiper>
        <vs-divider class="p-0 m-0" color="gray"  icon="star"></vs-divider> -->
        <!-- <hr class="bg-primary border-4"/> -->
<!--
      </vx-card>


    </div> -->
    <!-- <div class="pl-5 pr-5 ml-5 mr-5 pt-0 mt-0"> -->
      <vs-divider class="pt-1 mt-1 " color="gray"  icon="star"></vs-divider>

    <!-- </div> -->







    <div class="flex flex-col pl-2 pr-2 ml-2 mr-2 ">


      <div class="flex mb-5 h-40">
        <vx-card class=" mt-5  rounded pt-5 pb-5" >
          <div class="">
            <p class="text-center text-black text-3xl "> <strong>COMMENT CA MARCHE </strong></p>
          </div>

          <div class="flex mt-5 pb-8">
            <div class="w-1/3">
              <img class="responsive image h-full pr-0 mr-0 rounded " src="@/assets/images/pages/Step2.png" alt="banner">
              <div class="text-center pt-2 mt-3 pb-5 text-lg ">
                CHOISISSEZ VOTRE MATIÈRE
              </div>
            </div>
            <div class="pt-5 mt-5 text-center text-4xl container4">
              <p class="pl-3 ml-3"></p>
              <!-- <p class="pt-5 mt-5"> <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path class="heroicon-ui" d="M18.59 13H3a1 1 0 0 1 0-2h15.59l-5.3-5.3a1 1 0 1 1 1.42-1.4l7 7a1 1 0 0 1 0 1.4l-7 7a1 1 0 0 1-1.42-1.4l5.3-5.3z"/></svg></p> -->
            </div>

            <div class="w-1/3">
              <img class="responsive image h-full pr-0 mr-0 rounded " src="@/assets/images/pages/Step3.png" alt="banner">
              <div class="text-center pt-2 mt-3 pb-5 text-lg ">
                CHOISISSEZ VOTRE TEST À FAIRE
              </div>
            </div>

            <div class="pt-5 mt-5 text-center text-4xl container4">
              <p class="pl-3 ml-3"></p>
              <!-- <p class="pt-5 mt-5"> <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path class="heroicon-ui" d="M18.59 13H3a1 1 0 0 1 0-2h15.59l-5.3-5.3a1 1 0 1 1 1.42-1.4l7 7a1 1 0 0 1 0 1.4l-7 7a1 1 0 0 1-1.42-1.4l5.3-5.3z"/></svg></p> -->
            </div>

            <div class="w-1/3">
              <img class="responsive image h-full pr-0 mr-0 rounded" src="@/assets/images/pages/Step5.png" alt="banner">
              <div class="text-center mt-2 pt-2 pb-5 text-lg ">
                COMPOSEZ LE TEST CHOISI SUIVIT D'UNE CORRECTION
              </div>
            </div>


          </div>

          <!-- <div class="flex mt-5 pt-5">
            <div class="w-1/2">
              <img class="responsive image h-full pr-0 mr-0 " src="@/assets/images/pages/Step4.png" alt="banner">
            </div>

            <div class="pt-5 mt-5">
              <p class="pt-5 mt-5"> <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path class="heroicon-ui" d="M18.59 13H3a1 1 0 0 1 0-2h15.59l-5.3-5.3a1 1 0 1 1 1.42-1.4l7 7a1 1 0 0 1 0 1.4l-7 7a1 1 0 0 1-1.42-1.4l5.3-5.3z"/></svg></p>
            </div>
            <div class="w-1/2">
              <img class="responsive image h-full pr-0 mr-0 " src="@/assets/images/pages/Step5.png" alt="banner">
            </div>
          </div> -->


          <!-- <iframe class="ql-video ql-align-center" src="https://www.youtube.com/embed/QHH3iSeDBLo?showinfo=0" width="560" height="238"></iframe> -->
        </vx-card>

      </div>
      <vs-card class="rounded-none pt-5 mt-5 bg-white">
        <div class=" mt-5 ">
          <p class="text-center text-3xl"><strong>LES CLASSES</strong></p>
        </div>


        <div class="flex mb-4  w-full mt-2 ">
          <div class="px-4 py-2 m-2 w-1/3">
            <vs-card class="text-center cursor-pointer ml-5 mr-5 bg-black">
              <div slot="header" class="p-5">
                <h3 class="text-white">
                  CM2
                </h3>
              </div>
            </vs-card>
          </div>
          <div class="px-4 py-2 m-2 w-1/3">
            <router-link :to="{ name: 'page-knowledge', params: {} }">
              <vs-card class="text-center cursor-pointer ml-5 mr-5 bg-black">
                <div slot="header" class="p-5 cursor-pointer border-2 border-black border-solide">
                  <h3 class="text-white">
                    3ème
                  </h3>
                </div>
              </vs-card>

            </router-link>

          </div>

          <div class="px-4 py-2 m-2 w-1/3">
            <vs-card class="text-center cursor-pointer ml-5 mr-5 bg-black">
              <div slot="header" class="p-5">
                <h3 class="text-white">
                  T
                </h3>
              </div>
            </vs-card>
          </div>

        </div>

        <div class="flex mb-4">
          <div class="px-4 py-2 m-2 w-1/3">
            <vs-card class="text-center cursor-pointer ml-5 mr-5 bg-black">
              <div slot="header" class="p-5">
                <h3 class="text-white">
                  BIENTOT
                </h3>
              </div>
            </vs-card>
          </div>
          <div class="px-4 py-2 m-2 w-1/3">
            <vs-card class="text-center cursor-pointer ml-5 mr-5 bg-black">
              <div slot="header" class="p-5">
                <h3 class="text-white">
                  BIENTOT
                </h3>
              </div>
            </vs-card>
          </div>
          <div class="px-4 py-2 m-2 w-1/3">
            <vs-card class="text-center cursor-pointer ml-5 mr-5 bg-black">
              <div slot="header" class="p-5">
                <h3 class="text-white">
                  BIENTOT
                </h3>
              </div>
            </vs-card>
          </div>


        </div>


      </vs-card>



    </div>



    <!-- <div class="vx-row pt-1 mt-1 ">
      <router-link class="   w-full" :to="{ name: 'page-knowledge', params: {} }">
        <vs-button  class="   w-full flex items-center justify-center text-black uppercase..." size="large" type="relief" color="#F8F8F8">CLICKEZ ICI POUR LES COURS A EXERCICES </vs-button>
      </router-link>


    </div> -->






  </div>
</template>

<script>


import 'swiper/dist/css/swiper.min.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'

export default {
    data() {
        return {
          swiperOption: {
          spaceBetween: 30,
          effect: 'fade',
          autoplay: {
                   delay: 3500,
                   disableOnInteraction: false
          },
          // pagination: {
          //     el: '.swiper-pagination',
          //     clickable: true
          // },
          // navigation: {
          //     nextEl: '.swiper-button-next',
          //     prevEl: '.swiper-button-prev'
          // }
        }
    }
  },
    components: {
        swiper,
        swiperSlide
    },

}
</script>

<style lang="scss">
/*! rtl:begin:ignore */
.bg-image{
  background-image:url("../assets/images/pages/carousel/banner-63.jpg");
  // background-color: #2a0b16;
}
.bikus{
 color:darkgrey;
 white-space: nowrap;
 position: absolute;
 top: 50%;
 left: 50%;
 transform: translate(-40%, -40%);
 font-size: 3em;
 font-family: sans-serif;
 letter-spacing: 0.1em;
 transition: 0.3s;
 text-shadow: 1px 1px 0 grey, 1px 2px 0 grey, 1px 3px 0 grey, 1px 4px 0 grey,
   1px 5px 0 grey, 1px 6px 0 grey, 1px 7px 0 grey, 1px 8px 0 grey,
   5px 13px 15px black;
}
div.container4{
   position: relative
}

div.container4 strong{
  margin: 0;
  position: absolute;
  top: 35%;
  left: 50%;
  margin-right: -50%;
  transform: translate(-50%, -50%);
}


.swiper-container {
    height:500px;
    width: 100%;

    // position: absolute;
    // left: 50%;
    // top: 50%;
    // margin-left: -150px;
    // margin-top: -150px;
}

.image{
  // height: 400px;
  max-width:100%;
  max-height:100%
}

/*! rtl:end:ignore */
</style>
