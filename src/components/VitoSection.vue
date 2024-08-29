<script setup>
import Modal from '@/components/Modal.vue'
import {Swiper, SwiperSlide} from 'swiper/vue';
import 'swiper/css';
import { ref } from 'vue'

const props = defineProps(['isMobile', 'isTablet'])

const contentType = ref(null);
const showModal = ref(false);

const handleClickCard = (type) => {
  contentType.value = type;
  showModal.value = true;
}

const playCard = [
  { title: '여행기/탐방기', content: '꼭 한번 가야만하는 여정을 \n소개하는 스토리형 콘텐츠', color: '#F9587B', img: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/play-1.png'},
  { title: '웹예능', content: '출연진들의 대화 흐름 속에서\n자연스럽게 브랜드 상품을 \n설명하는 예능형 콘텐츠', color: '#57ADEE', img: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/play-2.png'},
  { title: '숏폼', content: '짧고 강렬하게 구매 동기와\n브랜드 인지를 형성시키는 \n숏츠, 릴스, 클립형 콘텐츠', color: '#FFD500', img: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/play-3.png'},
  { title: '스케치 코미디', content: '배우들의 연기력이 만드는\n몰입도와 웃음 포인트가 \n있는 드라마형 콘텐츠', color: '#2E67FE', img: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/play-4-1.png'},
  { title: '커머스', content: '파격적인 프로모션을 위해\n사전홍보 이후 구매링크를\n 공개하는 판매 목적 콘텐츠', color: '#8C33E5', img: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/play-5.png'},
];

const defaultHeight = 320;
const hoverHeight = 480;
const randomMinHeight = 240;
const randomMaxHeight = 360;
const heights = ref([300, 240, 480, 350, 270]);
const playCardContentShow = ref([false, false, true, false, false]);

const getHeight = (index) => {
  return heights.value[index] || defaultHeight;
};

const getSideHeight = (index) => {
  if (index === 1) {
    return getRandomHeight(30, 75)
  }

  return getRandomHeight(10, 20)
}

const handleMouseOver = (hoverIndex) => {
  heights.value = heights.value.map((height, index) => {
    return index === hoverIndex
      ? hoverHeight
      : getRandomHeight(randomMinHeight, randomMaxHeight);
  });

  playCardContentShow.value = playCard.map((_, index) => index === hoverIndex);
};

const getRandomHeight = (min, max) => {
  return Math.floor(Math.random() * (max - min + 1)) + min;
};

const handleSlideChange = (e) => {
  handleMouseOver(e.activeIndex)
}
</script>

<template>
  <section class="play-interaction-section">
    <div class="play-interaction-layout">
      <h3 class="play-interaction-h3 scroll-horizontal-action">체험형 협찬 플레이 <br> 다채로운 제작 콘텐츠</h3>
      <ul class="play-card-ul scroll-horizontal-action delay-200">
        <div class="play-card-side">
          <div class="play-card-side-item blue sub" :style="{
                  height: getSideHeight(0) + 'px'
              }"/>
          <div class="play-card-side-item yellow sub" :style="{
                  height: getSideHeight(0) + 'px'
              }"/>
          <div class="play-card-side-item blue main"
               :style="{
                  height: getSideHeight(1) + 'px'
              }"
          />
        </div>
        <swiper
          ref="mySwiper"
          @slideChange="handleSlideChange"
          :initialSlide="2"
          :slidesPerView="5"
          :centeredSlides="true"
          :spaceBetween="25"
          :grabCursor="true"
          :pagination="{
      clickable: true,
    }" v-if="props.isTablet || props.isMobile">
          <swiper-slide v-for="(play, index) in playCard" :key="index">
            <div v-if="index === 0" class="play-card-side left">
              <div class="play-card-side-item blue sub" :style="{
                  height: getSideHeight(0) + 'px'
              }"/>
              <div class="play-card-side-item yellow sub" :style="{
                  height: getSideHeight(0) + 'px'
              }"/>
              <div class="play-card-side-item blue main"
                   :style="{
                  height: getSideHeight(1) + 'px'
              }"
              />
            </div>
            <div v-if="index === 4" class="play-card-side right">
              <div class="play-card-side-item blue main" :style="{
                  height: getSideHeight(1) + 'px'
              }"/>
              <div class="play-card-side-item yellow sub" :style="{
                  height: getSideHeight(0) + 'px'
              }"/>
              <div class="play-card-side-item blue sub"
                   :style="{
                  height: getSideHeight(0) + 'px'
              }"
              />
            </div>
            <li
              :key="play.title"
              :style="{
        backgroundColor: play.color,
        height: getHeight(index) + 'px'
      }"
              class="play-card-li"
              @click="handleClickCard(play.title)"
            >
              <h3
                v-show="playCardContentShow[index]"
                :class="{
    'play-card-title': true,
    'text-black': index === 2
  }"
              >
                {{ play.title }}
              </h3>
              <p
                v-show="playCardContentShow[index]"
                :class="{
    'play-card-content': true,
    'text-black': index === 2
  }"
              >
                {{ play.content }}
              </p>
              <img class="play-card-img" :src="play.img" :style="{
      transform: playCardContentShow[index] ? 'scale(1.4) translateY(-30px)' : 'none'
    }"/>
              <img v-show="playCardContentShow[index]" class="vito-play-icon" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/vito-play.svg"/>
            </li>
          </swiper-slide>
        </swiper>
        <li
          v-if="!props.isTablet && !props.isMobile"
          v-for="(play, index) in playCard"
          :key="play.title"
          :style="{
        backgroundColor: play.color,
        height: getHeight(index) + 'px'
      }"
          class="play-card-li"
          @mouseover="() => handleMouseOver(index)"
          @click="() => handleClickCard(play.title)"
        >
          <h3
            v-show="playCardContentShow[index]"
            :class="{
    'play-card-title': true,
    'text-black': index === 2
  }"
          >
            {{ play.title }}
          </h3>
          <p
            v-show="playCardContentShow[index]"
            :class="{
    'play-card-content': true,
    'text-black': index === 2
  }"
          >
            {{ play.content }}
          </p>
          <img class="play-card-img" :src="play.img" :style="{
      transform: playCardContentShow[index] ? 'scale(1.4) translateY(-30px)' : 'none'
    }"/>
          <img v-show="playCardContentShow[index]" class="vito-play-icon" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/vito-play.svg"/>
        </li>
        <div class="play-card-side">
          <div class="play-card-side-item blue main" :style="{
                  height: getSideHeight(1) + 'px'
              }"/>
          <div class="play-card-side-item yellow sub" :style="{
                  height: getSideHeight(0) + 'px'
              }"/>
          <div class="play-card-side-item blue sub"
               :style="{
                  height: getSideHeight(0) + 'px'
              }"
          />
        </div>
      </ul>
    </div>
    <Modal v-if="showModal" @close="showModal = false" :contentType="contentType" :isMobile="isMobile" />
  </section>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
section {
  width: 100%;
}

li {
  list-style: none;
}

button {
  background: inherit ; border:none; box-shadow:none; border-radius:0; padding:0; overflow:visible; cursor:pointer;
}

.swiper {
  width: 100%;
  border-radius: 16px;
}

.swiper-slide {
  width: 100%;
  height: 100%;
  border-radius: 16px;
  background: transparent;
  position: relative;
  text-align: center;


  /* Center slide text vertically */
  display: flex;
  justify-content: center;
  align-items: center;
}

:deep(.swiper-wrapper) {
  align-items: center;
}

:deep(.container) {
  max-width: none;
}

:deep(.col-12) {
  padding: 0;
}

.scroll-horizontal-action {
  opacity: 0;
  transform: translateY(80px);
  transition: all 0.7s ease-out;
}

.scroll-horizontal-action.show {
  opacity: 1;
  transform: translateY(0);
}

.scroll-horizontal-action.delay-200 {
  transition-delay: 200ms;
}

.play-interaction-section {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 8px;
  padding: 120px 0;
  overflow: hidden;
  background: #FBFCFD;
}

.play-interaction-layout {
  display: flex;
  width: 1400px;
  max-width: 1400px;
  padding: 0 15px;
  margin: auto;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 40px;
}

.play-interaction-h3 {
  color: #292E33;
  text-align: center;
  font-size: 36px;
  font-style: normal;
  font-weight: 700;
  line-height: 150%;
}

.play-card-ul {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 480px;
  gap: 24px;
}

.play-card-side {
  display: flex;
  align-items: center;
  gap: 24px;
}

.play-card-side-item {
  border-radius: 300px;
  transition: height 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.play-card-side-item.main {
  width: 30px;
  height: 42px;
  background-color: blue;
}

.play-card-side-item.blue {
  background-color: #2e67fe;
}

.play-card-side-item.yellow {
  background-color: #ffd500;
}

.play-card-side-item.sub {
  width: 10px;
  height: 42px;
}

.play-card-li {
  display: flex;
  width: 224px;
  height: 320px;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  padding: 70px 0;
  border-radius: 400px;
  white-space: pre-line;
  overflow: hidden;
  position: relative;
  transition: height 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.play-card-title {
  color: #FFF;
  font-size: 22px;
  font-style: normal;
  font-weight: 700;
  line-height: 32px;
}

.play-card-content {
  color: #FFF;
  text-align: center;
  font-size: 15px;
  font-style: normal;
  font-weight: 400;
  line-height: 22px;
}

.text-black {
  color: #000;
}

.play-card-img {
  width: 100%;
  height: auto;
  object-fit: cover;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 8px;
  position: absolute;
  bottom: 0;
  transform: scale(1.0) translateY(0px);
  transition: transform 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.vito-play-icon {
  position: absolute;
  bottom: 5px;
  width: 160px;
  height: 160px;
  cursor: pointer;
}

@media (max-width: 991px) and (min-width: 768px) {
  .play-interaction-section {
    padding: 120px 0;
  }

  .play-card-side.left {
    position: absolute;
    left: -120px;
  }

  .play-card-side.right {
    position: absolute;
    right: -120px;
  }
}

@media (max-width: 767px) {
  .play-interaction-section {
    padding: 80px 0;
  }

  .play-card-ul {
    gap: 16px;
  }

  .play-card-side.left {
    position: absolute;
    left: -120px;
  }

  .play-card-side.right {
    position: absolute;
    right: -120px;
  }

}
</style>