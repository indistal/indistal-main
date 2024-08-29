<script setup>
import { onMounted, ref } from 'vue'

const props = defineProps(['isMobile', 'isTablet'])

const carouselData = [
  { type: 'instagram', text: '숏폼' },
  { type: 'youtube', text: '예능' },
  { type: 'blog', text: '탐방기' },
  { type: 'instagram', text: '예능' },
  { type: 'youtube', text: '드라마' },
  { type: 'blog', text: '여행기' },
  { type: 'instagram', text: '광고' },
  { type: 'youtube', text: '토크쇼' },
  { type: 'blog', text: '솔직리뷰' },
  { type: 'instagram', text: '웹툰' },
  { type: 'youtube', text: '인터뷰' },
];

const userCategory = ref(null);

const redirectToPage = (url) => {
  window.location.href = url
}

onMounted(() => {
  try {
    userCategory.value = window['logged_in_user']['user-category'][0];
  } catch {
    userCategory.value = null;
  }
})
</script>

<template>
  <section class="main-section">
    <div class="main-section-layout">
      <div class="main-text-wrapper">
        <div class="main-carousel-wrap scroll-horizontal-action">
          <div class="main-carousel">
            <div v-for="carousel in carouselData" class="main-carousel-container">
              <img class="instagram-logo" alt="instagram-logo" v-if="carousel.type === 'instagram'" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/instagram_logo.svg"/>
              <img class="youtube-logo" alt="youtube-logo" v-if="carousel.type === 'youtube' && !props.isMobile" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/youtube-logo-white.png"/>
              <img class="youtube-logo" alt="youtube-logo" v-if="carousel.type === 'youtube' && props.isMobile" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/youtube-logo-black.png"/>
              <img class="blog-logo" alt="blog-logo" v-if="carousel.type === 'blog'" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/naver_logo.png"/>
              <h2 class="main-carousel-h2 x">X</h2>
              <h2 class="main-carousel-h2">{{ carousel.text }}</h2>
            </div>
            <div class="main-carousel-container">
              <img class="instagram-logo" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/instagram_logo.svg"/>
              <h2 class="main-carousel-h2">X</h2>
              <h2 class="main-carousel-h2">숏폼</h2>
            </div>
          </div>
        </div>
        <div class="main-section-hero-title-wrapper scroll-horizontal-action">
          <h4 class="main-section-h4 "><span v-if="!props.isMobile && !props.isTablet">협찬의 방식을 바꾸다.</span> AI추천 콘텐츠 제작 협찬 </h4>
          <div class="main-section-title-wrapper">
            <h2 class="main-section-title">인플루언서 협찬 플랫폼</h2>
            <img class="indistal-play-logo" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/indistal-logo-play.png"/>
          </div>
        </div>
        <div v-if="!userCategory" class="main-section-btn-wrap scroll-horizontal-action">
          <button @click="() => redirectToPage('https://www.indistal.com/indistal-signup')" class="main-section-btn influencer login">회원가입</button>
          <button @click="() => redirectToPage('https://www.indistal.com/signin/#user-accounts2')" class="main-section-btn brand login">로그인</button>
        </div>
        <div v-if="userCategory === 'Brand'" class="main-section-btn-wrap scroll-horizontal-action">
          <button @click="() => redirectToPage('https://www.indistal.com/product/#product-list')" class="main-section-btn influencer">플레이 생성하기</button>
          <button @click="() => redirectToPage('https://www.indistal.com/my-play-list-brand')" class="main-section-btn brand">참여한 인디스탈</button>
        </div>
        <div v-if="userCategory === 'Indigo'" class="main-section-btn-wrap scroll-horizontal-action">
          <button @click="() => redirectToPage('https://www.indistal.com/invitation-indistal')" class="main-section-btn influencer">초대장 확인</button>
          <button @click="() => redirectToPage('https://www.indistal.com/my-play-indistal')" class="main-section-btn brand">콘텐츠 등록</button>
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

li {
  list-style: none;
}

button {
  background: inherit ; border:none; box-shadow:none; border-radius:0; padding:0; overflow:visible; cursor:pointer;
}

.scroll-opacity-action {
  opacity: 0;
  transition: all 1s ease-out;
}

.scroll-opacity-action.show {
  opacity: 1;
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

.scroll-horizontal-action.delay-200 {
  transition-delay: 200ms;
}

.main-section {
  position: relative;
  width: 100%;
  height: 560px;
  margin: auto;
  padding: 120px 0 166px 0;
  display: flex;
  justify-content: center;
  align-items: center;
  background: url('https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/main-banner-pc.png') center center no-repeat;
  background-size: cover;
}

.main-section-layout {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 1140px;
  max-width: 1140px;
  padding: 0 56px;
}

.main-text-wrapper {
  width: 100%;
  display: flex;
  flex-direction: column;
}

.main-carousel-wrap {
  height: 56px;
  overflow: hidden;
}

.main-carousel-container {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  gap: 4px;
  height: 56px;
}

.instagram-logo {
  width: 20.005px;
  height: 20px;
}

.blog-logo {
  width: 27px;
  height: 26px;
}

.youtube-logo {
  width: 76px;
  height: 16px;
}


.main-carousel-h2 {
  color: #FFF;
  font-size: 16px;
  font-style: normal;
  font-weight: 700;
  line-height: 24px;
}

.main-carousel-h2.x {
  font-weight: 500;
}

.main-section-hero-title-wrapper {
  display: flex;
  flex-direction: column;
  gap: 6px;
}

.main-section-h4 {
  color: #FFF;
  font-size: 26px;
  font-style: normal;
  font-weight: 400;
  line-height: 32px;
}

.main-section-title-wrapper {
  display: flex;
  align-items: flex-end;
  gap: 8px;
}

.main-section-title {
  color: #FFF;
  font-size: 36px;
  font-style: normal;
  font-weight: 700;
  line-height: 150%;
}

.main-section-btn-wrap {
  display: flex;
  align-items: center;
  gap: 16px;
  margin-top: 24px;
}

.main-section-btn {
  display: flex;
  width: auto;
  padding: 8px 16px 10px 16px;
  justify-content: center;
  align-items: center;
  font-size: 16px;
  font-style: normal;
  font-weight: 700;
  line-height: 24px;
  border-radius: 80px;
}

.main-section-btn.influencer {
  background: #FFF;
  color: #8B46FF;
  transition: all 0.2s ease-in-out;
}

.main-section-btn.influencer:hover {
  background: #8B46FF;
  color: #FFF;
}

.main-section-btn.brand {
  border: 2px solid #FFF;
  color: #FFF;
  transition: all 0.2s ease-in-out;
}

.main-section-btn.brand:hover {
  background: #FFF;
  color: #53ACF0;
}

.indistal-play-logo {
  width: 235px;
  height: 44px;
}

@media (max-width: 991px) and (min-width: 768px) {
  .main-section {
    padding: 120px 0;
  }

  .main-section-btn {
    color: #FFF;
    font-size: 12px;
    font-style: normal;
    font-weight: 700;
    line-height: 18px;
  }

  .main-section-h4 {
    color: #FFF;
    font-size: 32px;
    font-style: normal;
    font-weight: 700;
    line-height: 38px;
  }

  .main-section-title {
    color: #FFF;
    font-size: 24px;
    font-style: normal;
    font-weight: 500;
    line-height: 32px;
  }

  .main-section-title-wrapper {
    align-items: center;
  }
}

@media (max-width: 767px) {
  .main-section {
    padding: 10% 0 0;
    height: 667px;
    align-items: flex-start;
    background: url('https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/main-banner-mobile-2.png') center center no-repeat;
    background-size: cover;
  }

  .main-section-layout {
    justify-content: center;
    padding: 0 15px;
  }

  .main-text-wrapper {
    justify-content: flex-start;
    align-items: center;
    margin-top: 40px;
  }

  .main-carousel-container {
    justify-content: center;
  }

  .main-section-hero-title-wrapper {
    justify-content: flex-start;
  }

  .main-carousel-h2 {
    color: #12161A;
    font-size: 16px;
    font-style: normal;
    font-weight: 700;
    line-height: 24px;
  }

  .main-section-h4 {
    color: #12161A;
    font-size: 20px;
    font-style: normal;
    font-weight: 700;
    line-height: 28px;
    text-align: center;
  }

  .main-section-title-wrapper {
    align-items: flex-end;
  }

  .main-section-title {
    color: #292E33;
    font-size: 18px;
    font-style: normal;
    font-weight: 500;
    line-height: 28px;
  }

  .indistal-play-logo {
    width: 144px;
    height: 27px;
  }

  .main-section-btn-wrap {
    flex-direction: row-reverse;
    width: 100%;
    margin-top: 24px;
  }

  .main-section-btn {
    width: 100%;
    color: #FFF;
    font-size: 14px;
    font-style: normal;
    font-weight: 600;
    line-height: 24px;
    padding: 6px 16px 8px 16px;
  }

  .main-section-btn.influencer {
    border: 2px solid rgba(139, 70, 255, 0.25);
    background: rgba(205, 175, 255, 0.25);
    color: #8B46FF;
    transition: all 0.2s ease-in-out;
  }

  .main-section-btn.influencer:hover {
    border: 2px solid rgba(139, 70, 255, 0.25);
    background: #8B46FF;
    color: #FFF;
  }

  .main-section-btn.brand {
    border: 2px solid rgba(83, 172, 240, 0.25);
    background: rgba(83, 172, 240, 0.10);
    color: #53ACF0;
    transition: all 0.2s ease-in-out;
  }

  .main-section-btn.brand:hover {

    background: #53ACF0;
    color: #FFF;
  }
}
</style>