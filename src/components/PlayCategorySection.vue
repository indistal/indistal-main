<script setup>
import { ref } from 'vue'

const playCategory1 = [
  {title: "방송", imgSrc: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/broadcast.png', delay: 100},
  {title: "공연", imgSrc: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/show.png', delay: 200},
  {title: "전시", imgSrc: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/exhibition.png', delay: 300},
  {title: "여행", imgSrc: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/trip.png', delay: 400},
  {title: "스포츠", imgSrc: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/sports.png', delay: 500},
]

const playCategory2 = [
  {title: "레저", imgSrc: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/leisure.png', delay: 600},
  {title: "음식", imgSrc: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/food.png', delay: 700},
  {title: "힐링", imgSrc: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/healing.png', delay: 800},
  {title: "호텔", imgSrc: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/hotel.png', delay: 900},
  {title: "테마파크", imgSrc: 'https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/theme-park.png', delay: 1000},
]


const brandBtnHover = ref(false);
const toggleBrandBtnHover = (value) => {
  brandBtnHover.value = value;
}

const influBtnHover = ref(false);
const toggleInfluBtnHover = (value) => {
  influBtnHover.value = value
}

</script>

<template>
  <section class="play-category-section">
  <div class="play-category-wrapper">
    <ul class="play-category-ul">
      <div class="play-category-li-wrapper">
        <li class="play-category-li scroll-horizontal-action" v-for="play in playCategory1" :key="play.title" :class="`delay-${play.delay}`">
          <img class="play-category-img" :src="play.imgSrc"/>
          <p class="play-category-li-text">{{ play.title }}</p>
        </li>
      </div>
      <div class="play-category-li-wrapper">
        <li class="play-category-li scroll-horizontal-action" v-for="play in playCategory2" :key="play.title" :class="`delay-${play.delay}`">
          <img class="play-category-img" :src="play.imgSrc"/>
          <p class="play-category-li-text">{{ play.title }}</p>
        </li>
      </div>
    </ul>
    <div class="play-category-bottom scroll-horizontal-action">
      <div class="play-category-type brand">
        <h1 class="play-category-type-h1">브랜드</h1>
        <div class="play-category-type-bottom">
          <p class="play-category-type-content">성공적인 프로모션을 위해 <br>
            맞춤 플레이를 만들어 보세요.</p>
          <a href="https://drive.google.com/uc?export=download&id=1cMwYz5hW9MglxxwqPAahLzW4v6c7fYns" download>
            <button @mouseover="toggleBrandBtnHover(true)" @mouseleave="toggleBrandBtnHover(false)"
                    class="play-category-btn brand">
              <p>인디스탈 소개자료</p>
              <img class="icon" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/brand-download.svg" alt="brand-download"/>
            </button>
          </a>
        </div>
      </div>
      <div class="play-category-type influencer">
        <h1 class="play-category-type-h1">인플루언서</h1>
        <div class="play-category-type-bottom">
          <p class="play-category-type-content">내 채널과 연관된 플레이를 <br>
            AI에게 추천 받아요.</p>
          <a href="https://www.indistal.com/profile/#user-accounts3">
            <button @mouseover="toggleInfluBtnHover(true)" @mouseleave="toggleInfluBtnHover(false)" class="play-category-btn influencer">
              <p>미디어 추천 설정 가이드</p>
              <img class="play-category-btn-svg icon" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/influencer-arrow.svg" alt="brand-download"/>
            </button>
          </a>
        </div>
      </div>
    </div>
  </div>
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

a {
  text-decoration: none;
}

li {
  list-style: none;
}

button {
  background: inherit ; border:none; box-shadow:none; border-radius:0; padding:0; overflow:visible; cursor:pointer;
}

.scroll-horizontal-action {
  opacity: 0;
  transform: translateY(40px);
  transition: all 0.7s ease-out;
}

.scroll-horizontal-action.show {
  opacity: 1;
  transform: translateY(0);
}

.scroll-horizontal-action.delay-100 {
  transition-delay: 100ms;
}

.scroll-horizontal-action.delay-200 {
  transition-delay: 200ms;
}

.scroll-horizontal-action.delay-300 {
  transition-delay: 300ms;
}

.scroll-horizontal-action.delay-400 {
  transition-delay: 400ms;
}

.scroll-horizontal-action.delay-500 {
  transition-delay: 500ms;
}

.scroll-horizontal-action.delay-600 {
  transition-delay: 600ms;
}

.scroll-horizontal-action.delay-700 {
  transition-delay: 700ms;
}

.scroll-horizontal-action.delay-800 {
  transition-delay: 800ms;
}

.scroll-horizontal-action.delay-900 {
  transition-delay: 900ms;
}

.scroll-horizontal-action.delay-1000 {
  transition-delay: 1000ms;
}

.play-category-section {
  width: 100%;
  margin: auto;
  padding: 40px 0;
  displaY: flex;
  justify-content: center;
  align-items: center;

  background: #FFF;
}

.play-category-ul {
  display: flex;
}

.play-category-wrapper {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 48px;
  max-width: 1140px;
  flex: 1 0 0;
}

.play-category-ul {
  display: flex;
  align-items: center;
  align-self: stretch;
}

.play-category-li-wrapper {
  display: flex;
  align-items: center;
  flex: 1 0 0;
}

.play-category-li {
  flex: 1 0 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 8px;
  height: 100px;
  border-radius: 12px;
  cursor: pointer;
}

.play-category-li > .play-category-img {
  transition: transform 300ms ease-in-out;
}

.play-category-li:hover > .play-category-img {
  transform: rotate(-10deg);
}

.play-category-li:active > .play-category-img {
  transform: rotate(-5deg);
}

.play-category-img {
  width: 44px;
  height: 44px;
}

.play-category-li-text {
  color: #3D454D;
  text-align: center;
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: 24px;
}

.play-category-bottom {
  width: 100%;
  display: flex;
  align-items: flex-start;
  gap: 20px;
  align-self: stretch;
}

.play-category-type {
  display: flex;
  flex-direction: column;
  padding: 24px 32px;
  justify-content: flex-end;
  gap: 12px;
  flex: 1 0 0;

  border-radius: 16px;
  background: #FFF;
  box-shadow: 0px 4px 12px 0px rgba(0, 0, 0, 0.06);
}

.play-category-type-h1 {
  color: #292E33;
  font-size: 26px;
  font-style: normal;
  font-weight: 700;
  line-height: 32px;
}

.play-category-type-bottom {
  display: flex;
  justify-content: space-between;
}

.play-category-type-content {
  color: #292E33;
  font-size: 16px;
  font-style: normal;
  font-weight: 500;
  line-height: 24px;
}

.play-category-btn {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 8px;
  padding: 12px 16px;
  border-radius: 100px;
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: 24px;
  transition: all 0.2s ease-in-out;
  filter: brightness(100%);
}

.play-category-btn .icon {
  transition: filter 0.2s ease-in-out;
}

.play-category-btn.brand {
  border: 2px solid rgba(139, 70, 255, 0.25);
  background: linear-gradient(0deg, rgba(205, 175, 255, 0.25) 0%, rgba(205, 175, 255, 0.25) 100%), #FFF;
  color: #8B46FF;
}

.play-category-btn.brand:hover {
  border: 2px solid rgba(139, 70, 255, 0.25);
  background: #8B46FF;
  color: #FFF;
}

.play-category-btn.brand:hover .icon {
  filter: brightness(0) invert(1);
}

.play-category-btn.influencer {
  border: 2px solid rgba(83, 172, 240, 0.25);
  background: linear-gradient(0deg, rgba(83, 172, 240, 0.10) 0%, rgba(83, 172, 240, 0.10) 100%), #FFF;
  color: #53ACF0;
}

.play-category-btn.influencer:hover {
  background: #53ACF0;
  color: #FFF;

}

.play-category-btn.influencer:hover .icon {
  filter: brightness(400%);
}

.play-category-btn-svg {
  width: 24px;
  height: 24px;
}

@media (max-width: 991px) and (min-width: 768px) {
  .play-category-section {
  }

  .play-category-wrapper {
  }

  .play-category-ul {
    flex-direction: column;
    gap: 24px;
  }

  .play-category-li-wrapper {
    width: 100%;
  }

  .play-category-type-bottom {
    flex-direction: column;
    gap: 24px;
  }
}

@media (max-width: 767px) {
  .play-category-section {
    padding: 0 16px;
  }


  .play-category-bottom {
    flex-direction: column;
    align-items: center;
    width: 100%;
  }

  .play-category-type {
    width: 100%;
    height: 320px;
  }

  .play-category-type-bottom {
    flex-direction: column;
    gap: 24px;
  }

  .play-category-ul {
    flex-direction: column;
    gap: 24px;
  }

  .play-category-li-wrapper {
    width: 100%;
  }

  .play-category-wrapper {
    gap: 24px;
    padding: 40px 0;
  }

  .play-category-btn {
    justify-content: space-between;
  }
}
</style>