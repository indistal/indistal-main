<script setup>

</script>

<template>
  <section class="media-section">
    <img class="banner-img scroll-opacity-action delay-200" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/media-section-banner.png"/>
    <div class="media-content-wrapper">
      <h2 class="media-content-h2 scroll-horizontal-action delay-200">미디어 콘텐츠 산업과의 지속가능한 상생을 위해 <br>
        크리에이터들의 창작환경을 인디스탈이 지원합니다</h2>
      <ul class="media-content-ul scroll-horizontal-action delay-200">
        <div class="media-content-top">
          <li class="media-content-li purple">
            <div class="media-content-text-wrapper">
              <h4 class="media-content-text-h4 white">창작지원</h4>
              <h2 class="media-content-text-h2 white">다양한 창작 소재 <br>
                촬영 스튜디오 확보</h2>
            </div>
            <img class="media-content-img" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/media-content-1.png"/>
          </li>
          <li class="media-content-li reverse yellow">
            <div class="media-content-text-wrapper reverse">
              <h4 class="media-content-text-h4">자유여행</h4>
              <h2 class="media-content-text-h2">관광·레저 액티비티 <br>
                지역 테마 여행 플레이</h2>
            </div>
            <img class="media-content-img" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/media-content-2.png"/>
          </li>
        </div>
        <li class="media-content-li-last">
          <div class="media-content-text-wrapper">
            <h4 class="media-content-text-h4 white">브랜딩</h4>
            <h2 class="media-content-text-h2 white">브랜드 안전 <br>
              선한 영향력</h2>
          </div>
        </li>
      </ul>
    </div>
    <div class="media-content-wrapper">
      <h2 class="media-content-h2 bottom scroll-horizontal-action delay-200">즐거운 플레이가 <br>
        더 좋은 콘텐츠를 만듭니다.</h2>
      <div class="media-map-wrapper scroll-horizontal-action delay-200">
        <div class="media-map-content-wrapper">
          <div class="media-map-content-card">
            <h4 class="media-map-content-h4">플레이 기획</h4>
            <h2 class="media-map-content-h2">직접 체험 가능한 <br>
              플레이의 모든것</h2>
          </div>
          <div class="media-content-horizontal" />
          <div class="media-map-content-card">
            <h4 class="media-map-content-h4">인디스탈 모집</h4>
            <h2 class="media-map-content-h2">인디스탈 선정 <br>
              & 플레이 초대</h2>
          </div>
        </div>
        <div class="media-map-content-center">
          <div class="media-content-vertical"/>
          <div class="media-content-vertical"/>
        </div>
        <div class="media-map-content-wrapper">
          <div class="media-map-content-card">
            <h4 class="media-map-content-h4">플레이 체험</h4>
            <h2 class="media-map-content-h2">특별한 체험 <br>
              즐거운 기억</h2>
          </div>
          <div class="media-content-horizontal" />
          <div class="media-map-content-card">
            <h4 class="media-map-content-h4">콘텐츠 제작</h4>
            <h2 class="media-map-content-h2">높은 퀄리티 <br>
              더 큰 영향력</h2>
          </div>
        </div>
      </div>
      <h1 class="media-content-h1 scroll-horizontal-action delay-200">이제 인디스탈인지 <br> 먼저 확인하세요.</h1>
    </div>
  </section>
</template>

<style scoped>
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

.media-section {
  width: 100%;
  display: flex;
  gap: 120px;
  padding-bottom: 120px;
  flex-direction: column;
  align-items: center;

  background: linear-gradient(180deg, rgba(48, 49, 123, 0.00) 0%, rgba(0, 1, 86, 0.75) 25%, rgba(100, 0, 178, 0.75) 75%), #000;
}

.banner-img {
  width: 100%;
}

.media-content-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 1140px;
  width: 100%;
  gap: 40px;
}

.media-content-h2 {
  color: #E4EAF0;
  text-align: center;
  font-size: 36px;
  font-style: normal;
  font-weight: 600;
  line-height: 150%;
}

.media-content-h1 {
  color: #FFF;
  text-align: center;
  font-size: 64px;
  font-style: normal;
  font-weight: 600;
  line-height: 150%;
  margin-top: 64px;
}

.media-content-ul {
  width: 100%;
  display: flex;
  align-items: stretch;
  gap: 40px;
}

.media-content-top {
  display: flex;
  gap: 40px;
  flex: 2.5 1 0;
}

.media-content-li {
  display: flex;
  flex-direction: column;
  flex: 1 0 0;
  gap: 24px;
  padding-right: 40px;
  border-radius: 20px;
  box-shadow: 0 0 20px 0 rgba(139, 70, 255, 0.16);
}

.media-content-li-last {
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 24px;
  padding-right: 40px;
  border-radius: 20px;
  box-shadow: 0 0 20px 0 rgba(139, 70, 255, 0.16);
  background-image: url("https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/media-content-3.png");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-clip: border-box;
  flex: 1 1 0;
}

.media-content-li.reverse {
  flex-direction: column-reverse;
  padding-right: 0;
  padding-left: 40px;
}

.media-content-li.purple {
  background: linear-gradient(180deg, #8C33E5 0%, #BF40FF 100%), linear-gradient(180deg, #12161A 0%, #000 100%), #12161A;
}

.media-content-li.yellow {
  background: linear-gradient(180deg, #F7C919 0%, #FD0 100%);
}

.media-content-text-wrapper {
  display: flex;
  flex-direction: column;
  gap: 12px;
  align-items: flex-start;
  align-self: stretch;
  padding: 40px 40px 0 40px;
}

.media-content-text-wrapper.reverse {
  padding: 0 0 40px 0;
}

.media-content-text-wrapper > .white {
  color: #FFF;
}

.media-content-text-h4 {
  font-size: 20px;
  font-style: normal;
  font-weight: 700;
  line-height: 28px;
}

.media-content-text-h2 {
  font-size: 26px;
  font-style: normal;
  font-weight: 700;
  line-height: 32px;
}

.media-content-img {
  width: 100%;
  height: 100%;
}


.media-map-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 640px;
}

.media-map-content-wrapper {
  display: flex;
  align-items: center;
}

.media-map-content-card {
  display: flex;
  padding: 64px 0;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 12px;
  flex: 1 0 0;
  border-radius: 20px;
  border: 2px solid rgba(151, 71, 255, 0.50);
  background: rgba(205, 175, 255, 0.10);
  box-shadow: 0 0 20px 0 rgba(139, 70, 255, 0.16);
}

.media-map-content-h4 {
  color: #F7F9FA;
  text-align: center;
  font-size: 18px;
  font-style: normal;
  font-weight: 600;
  line-height: 28px;
}

.media-map-content-h2 {
  color: #FFF;
  text-align: center;
  font-size: 26px;
  font-style: normal;
  font-weight: 700;
  line-height: 32px;
}

.media-content-horizontal {
  width: 40px;
  height: 1px;
  background: #9747FF;
}

.media-map-content-center {
  display: flex;
  justify-content: space-between;
  padding: 0 150px;
}

.media-content-vertical {
  width: 1px;
  height: 40px;
  background: #9747FF;
}

@media (max-width: 991px) and (min-width: 768px) {
  .media-section {
    gap: 120px;
  }

  .media-content-h2 {
    font-size: 26px;
  }

  .media-content-h2.bottom {
    font-size: 36px;
    margin-top: 120px;
  }

  .media-content-h1 {
    font-size: 48px;
  }

  .media-content-ul {
    flex-direction: column;
  }

  .media-content-li {
    padding-right: 20px;
  }

  .media-content-li.reverse {
    padding-left: 20px;
  }

  .media-content-li-last {
    padding-bottom: 40px;
  }
}

@media (max-width: 767px) {
  .media-section {
    gap: 80px;
  }

  .media-content-h2 {
    font-size: 16px;
  }

  .media-content-h2.bottom {
    font-size: 26px;
    margin-top: 80px;
  }

  .media-content-h1 {
    font-size: 28px;
  }


  .media-map-wrapper {
    width: 100%;
  }

  .media-content-wrapper {
    width: 100%;
  }

  .media-content-ul {
    flex-direction: column;
  }

  .media-content-li {
    padding-right: 20px;
  }

  .media-content-li.reverse {
    padding-left: 20px;
  }

  .media-content-top {
    flex-direction: column;
    padding: 0 15px;
  }

  .media-content-li-last {
    margin: 0 15px;
    padding-bottom: 40px;
  }


  .media-map-content-wrapper {
    flex-direction: column;
    align-self: stretch;
    padding: 0 30px;
  }

  .media-map-content-card {
    width: 100%;
  }

  .media-map-content-h2 {
    font-size: 22px;
    font-weight: 500;
  }

  .media-content-horizontal {
    width: 1px;
    height: 20px;
  }

  .media-map-content-center {
    justify-content: center;
  }

  .media-content-vertical {
    height: 20px;
  }

  .media-content-vertical:first-child {
    display: none;
  }
}
</style>