<template>
<div class="wrapSwiper">
  <div class="container">
    <div class="title">
        <h3>복지소개</h3>
        <h4>기아가 당신의 여정에 함께합니다.</h4>
        <p>우리는 단지 자동차 제조 업체에만 머물지 않습니다.<br>
            이를 넘어, 모두에게 영감을 주는 시간과 공간을 만드는 사람들입니다.</p>
    </div>
    <div class="btnWrap">
        <button class="slick-arrow btnPrev">prev</button>
        <button class="slick-arrow btnNext">next</button>
    </div>
  </div>
  <div class="swiperView">

  <swiper            
            :modules="modules_03"
            v-bind="swiperOptions_03" 
            class="mySwiper_03"
          > 
            <swiper-slide v-for="(item, i) in sData" :key="i" class="sWrap">
              <a :href="sData[i].href">
                    <div class="simg">                   
                      <img :src="`images/04swiperView/${item.src}`" alt="">
                    </div>
                    <h3>{{sData[i].title}}</h3>
                    <p>{{sData[i].subtitle}}</p>
                  </a>
            </swiper-slide>
  </swiper>

  </div>
</div>  
</template>

<script>

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";

import "swiper/css/pagination";


// import required modules
import { Pagination } from "swiper";

export default {
  props:["sData"],
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules_03: [Pagination],
       swiperOptions_03:{
        slidesPerView:1,
        spaceBetween:3,
        breakpoints: {
          // 1280px 보다 클 경우
          1280: {
            slidesPerView: 5,
            spaceBetween: 3
          },
          700: {
            slidesPerView: 3,
            spaceBetween: 3
          }
         },
        loop:true,
        observer: true,
        observeParents: true,

        pagination:{
              type: "fraction"
             },                    
         }  
        }; 
    }
}
      
</script>


<style lang="scss">


.wrapSwiper{
    .title{
        font-family: 'Kia Signature', "맑은 고딕", "Malgun Gothic", 돋움, Dotum, sans-serif;
        color: #05141F;
        padding: 30px 0; 
        h3{       
            font-weight: 700;
            font-size: 50px;
            padding: 20px 0;                  
        }
        h4{
            font-weight: 400;
            font-size: 30px;
            line-height: 50px; 
        }
        p{
            font-weight: 400;
            font-size: 16px;
            line-height: 24px;
            color:#848C91;
        }              
    }
    .btnWrap{
        display: flex;
        justify-content: flex-end;      
        .slick-arrow{
            width:42px; height:42px; margin-left:12px;
            background-repeat:no-repeat; background-size:cover;
            overflow:hidden; text-indent:-9999px;
            :first-child { margin-left:0px; }       
            &.btnPrev{background-image:url("../assets/arrow-prev.svg");}
        &.btnNext{background-image:url("../assets/arrow-next.svg");} 
        }
        
     

    }
    .swiperView{
        .sWrap{ 
            padding: 50px;          
            .simg{           
                img{
                    height:300px;
                    padding-bottom:30px;
                }                
            }
            h3{
                    font-family: 'Kia Signature';                
                    font-weight: 700;
                    font-size: 24px;
                    line-height: 29px;
                    color: #05141F;
                    padding-bottom: 15px;
                }
            p{
                font-family: 'Kia Signature';    
                font-weight: 400;
                font-size: 16px;
                line-height: 24px;
                color: #666666;
            }    
         }
    }

}

</style>