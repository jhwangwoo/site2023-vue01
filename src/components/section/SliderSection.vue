<template>
  <section id="sliderSection" :class="attr">
    <div class="slider__inner containers">
      <h2 class="blind">배너 슬라이더</h2>
      <div class="slider__img">
        <swiper
          :modules="modules"
          :slides-per-view="1"
          :space-between="50"
          navigation
          :pagination="{ clickable: true }"
          :autoplay="{
            delay: 2500,
            disableOnInteraction: false,
          }"
          @swiper="onSwiper"
          @slideChange="onSlideChange"
        >
          <swiper-slide v-for="(slider, index) in sliders" :key="index">
            <div class="slider s1 container">
              <div class="text">
                <h3 v-html="slider.title"></h3>
                <p v-html="slider.desc"></p>
                <a href="#" class="more button-red">더 알아보기</a>
              </div>
              <div class="img" aria-label="hidden">
                <img :src="slider.iconimage1" :alt="slider.title" />
                <img :src="slider.iconimage2" :alt="slider.title" />
                <img :src="slider.iconimage3" :alt="slider.title" />
              </div>
              <div class="circle" aria-label="hidden">
                <span class="circle c1"></span>
                <span class="circle c2"></span>
                <span class="circle c3"></span>
                <span class="circle c4"></span>
                <span class="circle c5"></span>
              </div>
            </div>
          </swiper-slide>
        </swiper>
      </div>
      <!-- <div class="slider__btn">
        <router-Link to="/" class="left"
          ><span class="ir">이전이미지</span></router-Link
        >
        <router-Link to="/" class="right"
          ><span class="ir">다음이미지</span></router-Link
        >
      </div>
      <div class="slider__dot">
        <router-Link to="/" class="dot active"
          ><span class="ir">1번이미지</span></router-Link
        >
        <router-Link to="/" class="dot"
          ><span class="ir">2번이미지</span></router-Link
        >
        <router-Link to="/" class="dot"
          ><span class="ir">3번이미지</span></router-Link
        >
      </div> -->
    </div>
  </section>
</template>
<script>
import { Navigation, Pagination, A11y, Autoplay } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";
export default {
  props: {
    attr: {
      type: String,
      required: true,
    },
  },
  data: function () {
    return {
      sliders: [
        {
          title: "science <br />Technology",
          desc: "과학은 어떤 것이든 진실을 찾고<br/>이해하기 위해 끊임없이 탐구하는 모험입니다.",
          iconimage1: "./images/slider/slidericon01.png",
          iconimage2: "./images/slider/slidericon02.png",
          iconimage3: "./images/slider/slidericon03.png",
        },
        {
          title: "science <br />Technology",
          desc: "과학은 어떤 것이든 진실을 찾고<br/>이해하기 위해 끊임없이 탐구하는 모험입니다.",
          iconimage1: "./images/slider/slidericon04.png",
          iconimage2: "./images/slider/slidericon05.png",
          iconimage3: "./images/slider/slidericon06.png",
        },
        {
          title: "science <br />Technology",
          desc: "과학은 어떤 것이든 진실을 찾고<br />이해하기 위해 끊임없이 탐구하는 모험입니다.",
          iconimage1: "./images/slider/slidericon07.png",
          iconimage2: "./images/slider/slidericon08.png",
          iconimage3: "./images/slider/slidericon09.png",
        },
      ],
    };
  },
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log("slide change");
    };
    return {
      onSwiper,
      onSlideChange,
      modules: [Navigation, Pagination, A11y, Autoplay],
    };
  },
};
</script>

<style lang="scss">
@import "../../assets/scss/setting/mixins.scss";

.slider__wrap {
}
.slider__inner {
  position: relative;

  .slider__img {
    .slider {
      height: 500px;
      .text {
        h3 {
          font-size: 110px;
          font-weight: 800;
          text-transform: uppercase;
          line-height: 1;
          margin-bottom: 40px;
        }
        p {
          font-size: 24px;
          line-height: 1.2;
          margin-bottom: 50px;
        }
        .more {
          font-size: 18px;
        }
      }
      .img {
        position: absolute;
        right: 0;
        top: -120px;
        width: 600px;
        height: 600px;
        background-image: url(@/assets/images/slider/sliderimageBg.png);

        img {
          &:nth-child(1) {
            position: absolute;
            width: 200px;
            left: 150px;
            top: 100px;
          }
          &:nth-child(2) {
            position: absolute;
            width: 250px;
            right: 5px;
            top: 250px;
          }
          &:nth-child(3) {
            position: absolute;
            width: 200px;
            bottom: 30px;
            left: 90px;
          }
        }
      }
      .circle {
        span {
          display: block;
          position: absolute;
          left: 50%;
          top: 50%;
          width: 20px;
          height: 20px;
          border-radius: 50%;
        }
        span:nth-child(1) {
          background-color: var(--button_green);
          left: 50%;
          top: 70%;
          width: 30px;
          height: 30px;
        }
        span:nth-child(2) {
          background-color: var(--button_red);
          top: 20%;
          left: -10%;
          width: 70px;
          height: 70px;
        }
        span:nth-child(3) {
          background-color: var(--button_red);
          left: 100%;
          top: 10%;
        }
        span:nth-child(4) {
          background-color: var(--button_blue);
          left: 17%;
          top: -30px;
          width: 20px;
          height: 20px;
        }
        span:nth-child(5) {
          background-color: var(--button_blue);
          left: 100%;
          top: 80%;
          width: 50px;
          height: 50px;
        }
      }
    }
  }

  .slider__btn {
    > a {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      width: 22px;
      height: 40px;
      transition: opacity 0.3s;

      &hover {
        opacity: 0.5;
      }
    }
    .left {
      left: 20px;
      background-image: url(@/assets/images/slider/slider_left.png);
    }
    .right {
      right: 20px;
      background-image: url(@/assets/images/slider/slider_right.png);
    }
  }
  .slider__dot {
    position: absolute;
    left: 50%;
    bottom: -80px;
    transform: translateX(-50%);
    a {
      display: inline-block;
      width: 16px;
      height: 16px;
      border-radius: 50%;
      margin: 0 5px;
      border: 4px solid #ff3344;
      background-color: #ff3344;
      box-shadow: 0 0 0 3px transparent;
      &.active {
        box-shadow: 0 0 0 3px #ff3344;
        border-width: 4px;
        background-color: #fff;
      }
    }
  }
}
</style>
