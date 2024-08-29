<script setup>

</script>

<template>
  <section class="intro-section-1">
    <div class="intro-wrapper">
      <div class="intro-frame">
        <div class="intro-frame-wrap">
          <div class="intro-frame-top-left scroll-horizontal-action delay-200">
            <div class="intro-frame-top-left-text-wrap">
              <h4 class="intro-frame-top-left-h4">익스클루시브 커뮤니티,</h4>
              <img class="indistal-play-logo" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/indistal-logo-play.png" alt="indistal-logo"/>
              <p class="intro-frame-top-left-p">연예인, 셀럽, 인플루언서, 분야별 전문가, 아티스트,
                네이버 공식 인플루언서, 유튜버 실버부터 플레이 가능합니다.</p>
            </div>
            <div class="youtube-gold-silver-wrapper">
              <img class="youtube-gold-silver" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/youtube-silver-gold.png" alt="youtube-silver-gold"/>
            </div>
          </div>
        </div>
        <div class="intro-frame-wrap">
          <div class="intro-frame-bottom-left scroll-horizontal-action delay-200">
            <div class="intro-frame-bottom-left-text-wrap">
              <h4 class="intro-frame-bottom-left-h4">캠페인이 아니다</h4>
              <h2 class="intro-frame-bottom-left-h2">인디스탈 플레이다</h2>
              <p class="intro-frame-bottom-left-p">광고도 리뷰도 아닌 브랜드 협찬 플레이</p>
            </div>
            <img class="play-card-dummy" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/play-card-dummy.png" />
          </div>
          <div class="intro-frame-bottom-right scroll-horizontal-action delay-200">
            <h1 class="intro-frame-bottom-right-h1">다양한 잠재력 <br> 10종의 플레이</h1>
            <div class="vertical-scrolling-wrapper">
              <div class="scrolling-text">
                <h2>방송</h2>
                <h2>공연</h2>
                <h2>전시</h2>
                <h2>스포츠</h2>
                <h2>여행</h2>
                <h2>레저</h2>
                <h2>음식</h2>
                <h2>힐링</h2>
                <h2>호텔</h2>
                <h2>테마파크</h2>
                <!-- Duplicate for seamless scrolling -->
                <h2>방송</h2>
                <h2>공연</h2>
                <h2>전시</h2>
                <h2>스포츠</h2>
                <h2>여행</h2>
                <h2>레저</h2>
                <h2>음식</h2>
                <h2>힐링</h2>
                <h2>호텔</h2>
                <h2>테마파크</h2>
              </div>
            </div>
            <p class="intro-frame-bottom-right-p">각 카테고리에서 매번 다양한 경험을 선사해 머릿속 구상했던 콘텐츠가 온전히 빛을 보도록 크리에이터의 무한한 가능성을 지원합니다.</p>
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

.scroll-horizontal-action.delay-200 {
  transition-delay: 200ms;
}

.intro-section-1 {
  width: 100%;
  margin: auto;
  padding: 120px 0;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #FBFCFD;
}

.intro-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0 15px;
  width: 100%;
}

.intro-frame {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 32px;
  align-self: stretch;
  width: 100%;
  max-width: 1140px;
}

.intro-frame-wrap {
  width: 100%;
  display: flex;
  align-items: center;
  gap: 20px;
  align-self: stretch;
}

.intro-frame-top-left {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 64px;
  padding: 48px 64px 0 64px;
  border-radius: 20px;
  background: #FFF;
  box-shadow: 0 4px 12px 0 rgba(0, 0, 0, 0.06);
  height: 100%;
}

.intro-frame-top-left-text-wrap {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 10px;
  flex-basis: 50%;
  padding-bottom: 64px;
}

.intro-frame-top-left-h4{
  color: #292E33;
  font-size: 20px;
  font-style: normal;
  font-weight: 700;
  line-height: 28px;
}

.indistal-play-logo {
  width: 100%;
  max-width: 337px;
  height: auto;
  max-height: 64px;
}

.intro-frame-top-left-p {
  color: #3D454D;
  font-size: 18px;
  font-style: normal;
  font-weight: 500;
  line-height: 28px;
}

.youtube-gold-silver-wrapper {
  width: 100%;
  height: 100%;
  flex-basis: 50%;
}

.youtube-gold-silver {
  width: 100%;
  height: 100%;
}

.intro-frame-bottom-left {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  align-self: stretch;
  padding-top: 48px;
  gap: 48px;
  border-radius: 20px;
  background: #FFF;
  box-shadow: 0 4px 12px 0 rgba(0, 0, 0, 0.06);
  flex: 1 0 0;
}

.intro-frame-bottom-left-text-wrap {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.intro-frame-bottom-left-h4 {
  color: #292E33;
  text-align: center;
  font-size: 20px;
  font-style: normal;
  font-weight: 700;
  line-height: 28px;
}

.intro-frame-bottom-left-h2 {
  color: #0091FF;
  text-align: center;
  font-size: 36px;
  font-style: normal;
  font-weight: 700;
  line-height: 150%;
}

.intro-frame-bottom-left-p {
  margin-top: 24px;
  color: #3D454D;
  text-align: center;
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: 140%;
}

.play-card-dummy {
  width: 100%;
}

.intro-frame-bottom-right {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 24px;
  border-radius: 20px;
  width: 100%;
  height: 100%;
  box-shadow: 0 4px 8px 0 rgba(218, 224, 230, 0.38);
  overflow: hidden;
  flex: 1 0 0;
}

.intro-frame-bottom-right::after {
  position: absolute;
  top: 0;
  left: 0;
  filter: brightness(60%);
  opacity: 1;
  transition: opacity 1s cubic-bezier(0.42, 0, 0.58, 1);
  width: 100%;
  height: 100%;
  border-radius: 20px;
  content: "";
  background-image: url("https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/int-card-PC.png");
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

.vertical-scrolling-wrapper {
  z-index: 1;
  display: flex;
  align-items: center;
  gap: 24px;
  width: 100%;
  height: 80px;
  overflow: hidden;
  opacity: 0.4;
}

.scrolling-text {
  display: flex;
  gap: 24px;
  animation: scroll-right 10s linear infinite;
}

.scrolling-text h2 {
  color: #FFF;
  font-size: 80px;
  font-style: normal;
  font-weight: 700;
  line-height: 100%;
  white-space: nowrap;
}

@keyframes scroll-right {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(-50.3%);
  }
}

.intro-frame-bottom-right-h1 {
  color: #FFF;
  font-size: 36px;
  font-style: normal;
  font-weight: 700;
  line-height: 125%;
  z-index: 1;
  padding: 48px 48px 0 48px;
}

.intro-frame-bottom-right-p {
  color: #FFF;
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: 140%;
  z-index: 1;
  padding: 0 48px 48px 48px;
}

.parallax-scrolling-wrapper h4 {
  color: #FFF;
  text-align: right;
  font-size: 32px;
  font-style: normal;
  font-weight: 700;
  line-height: 125%;
}

@media (max-width: 991px) and (min-width: 768px) {
  .intro-section-1 {
    padding: 120px 0;
  }

}

@media (max-width: 767px) {
  .intro-section-1 {
    padding: 80px 16px;
  }

  .intro-wrapper {
    width: 100%;
    max-width: 100%;
  }

  .intro-frame {
    width: 100%;
  }

  .intro-frame-wrap {
    flex-direction: column;
    align-items: center;
  }

  .intro-frame-top-left {
    padding: 0;
    flex-direction: column;
    gap: 24px;
    flex: unset;
  }

  .youtube-gold-silver-wrapper, .youtube-gold-silver {
    border-radius: 0 0 16px 16px;
  }

  .intro-frame-top-left-text-wrap {
    padding: 48px 24px 0 24px;
  }

  .intro-frame-bottom-right-h1, intro-frame-bottom-right-p {
    text-align: center;
  }

  .intro-frame-bottom-right {
    gap: 64px;
    flex: unset;
  }

  .intro-frame-top-left-p {
    color: #3D454D;
    font-size: 16px;
    font-style: normal;
    font-weight: 400;
    line-height: 140%;
  }
}

@media (max-width: 580px) {
}
</style>