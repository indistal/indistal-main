<script setup>
import { onMounted, ref } from 'vue'

import MainSection from '@/components/MainSection.vue'
import PlayCategorySection from '@/components/PlayCategorySection.vue'
import VitoSection from '@/components/VitoSection.vue'
import CardSection from '@/components/CardSection.vue'
import PlayGuide from '@/components/PlayGuide.vue'
import MediaSection from '@/components/MediaSection.vue'
import FooterSection from '@/components/FooterSection.vue'

const userCategory = ref(null);
const isMobile = ref(window.matchMedia('(max-width: 767px)').matches);
const isTablet = ref(window.matchMedia('(min-width: 768px) and (max-width: 991px)').matches);

const handleResize = () => {
  isMobile.value = window.matchMedia('(max-width: 767px)').matches;
  isTablet.value = window.matchMedia('(min-width: 768px) and (max-width: 991px)').matches;
};

onMounted(() => {
  // TODO: SOFTR 자체의 컨테이너 여백 제거
  const customCodeElement = document.querySelector('#custom-code3');
  if (customCodeElement) {
    const softrContainer = customCodeElement.querySelector('.container');
    const softrCol12 = customCodeElement.querySelector('.col-12');

    if (softrContainer) {
      softrContainer.style.maxWidth = 'none';
    }
    if (softrCol12) {
      softrCol12.style.padding = '0';
    }
  }

  // TODO: 로그인 유저 및 브랜드/인플루언서 회원 구분

  try {
    userCategory.value = window['logged_in_user']['user-category'][0];
  } catch {
    userCategory.value = null;
  }

  // TODO: 요소 스크롤 액션 추가
  function isElementInViewport(el) {
    const rect = el.getBoundingClientRect();
    const viewHeight = window.innerHeight || document.documentElement.clientHeight;
    const paddingOffset = parseFloat(window.getComputedStyle(el).paddingTop) || 0;

    return (
      rect.top + paddingOffset <= viewHeight &&
      rect.bottom >= 0
    );
  }

  function applyAnimationOnScroll() {
    const horizontalElements = document.querySelectorAll('.scroll-horizontal-action');
    const opacityElements = document.querySelectorAll('.scroll-opacity-action');
    horizontalElements.forEach(element => {
      if (isElementInViewport(element)) {
        element.classList.add('show');
      }
    });
    opacityElements.forEach(element => {
      if (isElementInViewport(element)) {
        element.classList.add('show');
      }
    });
  }

  window.addEventListener('load', applyAnimationOnScroll);
  window.addEventListener('scroll', applyAnimationOnScroll);

  // TODO: mediaQuery
  const mediaQueryList = window.matchMedia('(max-width: 767px)');
  const mediaQueryListTablet = window.matchMedia('(min-width: 768px) and (max-width: 991px)');

  handleResize(mediaQueryList); // 초기 상태 설정
  mediaQueryList.addEventListener('change', handleResize); // 리스너 등록
  mediaQueryListTablet.addEventListener('change', handleResize); // 리스너 등록

  // TODO: 메인 섹션 텍스트 슬라이드
  const carouselWrapper = document.querySelector('.main-carousel');
  const carouselContainer = document.querySelectorAll('.main-carousel .main-carousel-container');

  let currentIndex = 0;
  const slideHeight = 56;

  function nextSlide() {
    currentIndex++;
    carouselWrapper.style.transition = 'transform 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275)';
    carouselWrapper.style.transform = 'translateY(' + (-slideHeight * currentIndex) + 'px)';
  }

  setInterval(() => {
    nextSlide();
    if (currentIndex === carouselContainer.length - 1) {
      setTimeout(() => {
        carouselWrapper.style.transition = 'none';
        carouselWrapper.style.transform = 'translateY(0)';
        currentIndex = 0;
      }, 1000);
    }
  }, 3000);
});
</script>

<template>
  <MainSection :isMobile="isMobile" :isTablet="isTablet"/>
  <PlayCategorySection />
  <VitoSection :isMobile="isMobile" :isTablet="isTablet"/>
  <CardSection />
  <PlayGuide :isMobile="isMobile" />
  <MediaSection />
  <FooterSection />

  <a href="https://www.indistal.com/indistalcorp" class="indistal-fixed" >
    <p class="indistal-fixed-text">Powered by</p>
    <img class="indistal-play-logo" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/indistal-logo.png" alt="indistal-logo"/>
  </a>
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

a {
  text-decoration: none;
}

::-webkit-scrollbar {
  width: 12px; /* 수직 스크롤바의 너비 */
  height: 12px; /* 수평 스크롤바의 높이 */
}

/* 스크롤바 트랙 (스크롤바가 이동하는 영역) */
::-webkit-scrollbar-track {
  background: #f1f1f1; /* 트랙의 배경색 */
  border-radius: 10px; /* 트랙의 모서리를 둥글게 */
}

/* 스크롤바 핸들 (스크롤바의 드래그 가능한 부분) */
::-webkit-scrollbar-thumb {
  background: #888; /* 핸들의 배경색 */
  border-radius: 10px; /* 핸들의 모서리를 둥글게 */
}

/* 스크롤바 핸들이 호버될 때 */
::-webkit-scrollbar-thumb:hover {
  background: #555; /* 핸들의 배경색 (호버 시) */
}

/* scroll animation*/
.scroll-horizontal-action {
  opacity: 0;
  transform: translateY(80px);
  transition: all 0.7s ease-out;
}

.scroll-horizontal-action.show {
  opacity: 1;
  transform: translateY(0);
}

.indistal-fixed {
  position: fixed;
  left: 24px;
  bottom: 24px;
  display: flex;
  align-items: flex-end;
  gap: 8px;
  cursor: pointer;
}

.indistal-fixed-text {
  color: #53ACF0;
  font-size: 10px;
  font-style: normal;
  font-weight: 300;
  line-height: 100%;
}

.indistal-play-logo {
  width: 63px;
  height: 14px;
}
</style>
