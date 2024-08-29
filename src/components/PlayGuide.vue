<script setup>
const props = defineProps(['isMobile']);

const redirectToPage = (url) => {
  window.location.href = url
}
</script>

<template>
  <section class="play-guide-section">
    <div class="play-guide-wrapper">
      <div class="play-guide-title-wrapper scroll-horizontal-action delay-200">
        <h4 class="play-guide-h4">플레이 시작하기</h4>
        <h1 class="play-guide-h1">단순한 플레이 참여방법</h1>
        <p class="play-guide-p">원하는 플레이를 선택해 신청하면 <br v-if="props.isMobile">
          브랜드가 초대하는 프로세스 <br>
          이제 콘텐츠 제작에만 집중하세요. </p>
      </div>
      <div class="play-guide-card-layout">
        <div class="play-guide-card-line-wrapper scroll-horizontal-action delay-200">
          <div class="play-guide-card-wrapper ">
            <div class="play-guide-text-wrapper">
              <h4 class="play-guide-card-h4">Step 1</h4>
              <h3 class="play-guide-card-h3">명확한 협찬 가이드</h3>
              <p class="play-guide-card-p">다양한 액티비티 협찬, 창작 소재, 테마 공간 등 브랜드와 크리에이터 모두가 상생하는 플레이</p>
            </div>
            <div class="play-guide-card-img-wrapper card-1">
              <img class="play-guide-card-img" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/play-guide-step-1-1.png"/>
              <div class="blur-wrapper"/>
            </div>
          </div>
          <div class="play-guide-card-wrapper card-2">
            <div class="play-guide-text-wrapper">
              <h4 class="play-guide-card-h4">Step 2</h4>
              <h3 class="play-guide-card-h3">원하는 플레이 선택 콘텐츠 기획안 입력</h3>
            </div>
            <div class="play-guide-card-img-wrapper card-2">
              <img class="play-guide-card-img" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/play-guide-step-2-3.png"/>
              <div class="blur-wrapper"/>
            </div>
          </div>
        </div>
        <div class="play-guide-card-line-wrapper scroll-horizontal-action delay-200">
          <div class="play-guide-card-wrapper-b card-3">
            <div class="play-guide-card-img-wrapper-b card-3">
              <img v-if="props.isMobile" class="play-guide-card-img" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/play-guide-step-3-1.png"/>
              <div class="blur-wrapper card-3"/>
            </div>
            <div class="play-guide-text-wrapper-b">
              <h4 class="play-guide-card-h4">Step 3</h4>
              <h3 class="play-guide-card-h3">브랜드에서 플레이 참여자 선정 후 초대장 발송</h3>
            </div>
          </div>
          <div class="play-guide-card-wrapper-b card-4">
            <div class="play-guide-card-img-wrapper-b card-4">
              <img v-if="props.isMobile" class="play-guide-card-img" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/play-guide-step-4-4.png"/>
              <div v-if="!props.isMobile" class="blur-wrapper card-4"/>
            </div>
            <div class="play-guide-text-wrapper-b">
              <h4 class="play-guide-card-h4">Step 4</h4>
              <h3 class="play-guide-card-h3">제작한 콘텐츠를 콘텐츠 등록 페이지에 입력</h3>
            </div>
          </div>
        </div>
      </div>
      <div class="play-guide-start-wrapper scroll-horizontal-action delay-200">
        <h2 class="play-guide-start-h2"> AI가 추천하는 콘텐츠 제작 협찬 <br>
          인디스탈 플레이, 지금 경험해 보세요!</h2>
        <button @click="() => redirectToPage('https://www.indistal.com/signin/#user-accounts2')" class="play-guide-start-btn">지금 플레이 시작하기</button>
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

.play-guide-section {
  width: 100%;
  margin: auto;
  padding: 120px 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background: #EDF1F5;
}

.play-guide-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  max-width: 1140px;
  height: 100%;
  gap: 24px;
  padding: 0 15px;
}

.play-guide-title-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  align-self: stretch;
}

.play-guide-h4 {
  color: #292E33;
  text-align: center;
  font-size: 20px;
  font-style: normal;
  font-weight: 700;
  line-height: 28px;
}

.play-guide-h1{
  color: #292E33;
  text-align: center;
  font-size: 36px;
  font-style: normal;
  font-weight: 700;
  line-height: 150%;
}

.play-guide-p {
  color: #3D454D;
  text-align: center;
  font-size: 18px;
  font-style: normal;
  font-weight: 500;
  line-height: 28px;
  margin-top: 12px;
}

.play-guide-card-layout {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 24px;
}

.play-guide-card-line-wrapper {
  width: 100%;
  display: flex;
  align-items: center;
  gap: 24px;
  align-self: stretch;
}

.play-guide-card-wrapper {
  display: flex;
  height: 560px;
  flex-direction: column;
  align-items: center;
  flex: 1 0 0;
  border-radius: 16px;
  background: #FFF;
  box-shadow: 0 4px 8px 0 rgba(218, 224, 230, 0.38);
  overflow: hidden;
  position: relative;
}

.play-guide-text-wrapper {
  display: flex;
  padding: 40px 40px 0 40px;
  flex-direction: column;
  align-items: flex-start;
  align-self: stretch;
  gap: 4px;
}

.play-guide-card-h4 {
  color: #803DFF;
  font-size: 16px;
  font-style: normal;
  font-weight: 700;
  line-height: 24px;
}

.play-guide-card-h3 {
  color: #292E33;
  font-size: 20px;
  font-style: normal;
  font-weight: 700;
  line-height: 28px;
  margin-top: 8px;
}

.play-guide-card-p {
  color: #3D454D;
  font-size: 18px;
  font-style: normal;
  font-weight: 500;
  line-height: 28px;
  word-break: keep-all; /* 단어 단위로 줄바꿈 */
  white-space: normal; /* 줄바꿈이 가능하도록 설정 */
}

.play-guide-card-img-wrapper {
  position: absolute;
  bottom: 0;
  width: 100%;
  overflow: hidden;
}

.play-guide-card-img-wrapper.card-1 {
  position: inherit;
  display: flex;
  justify-content: center;
  width: 100%;
  flex: 1 0 0;
  background: url("https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/play-guide-step-1.png") no-repeat center center;
  background-size: contain;
}

.play-guide-card-img-wrapper.card-2 {
  position: inherit;
  display: flex;
  justify-content: center;
  flex: 1 0 0;
  background: url("https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/play-guide-step-2-1.png") no-repeat center center;
  background-size: contain;
}

.play-guide-card-img {
  display: flex;
  justify-content: center;
  align-items: center;
  flex: 1 0 0;
  align-self: stretch;
  position: absolute;
  bottom: 0;
  min-width: 240px;
}

.blur-wrapper {
  width: 100%;
  height: 40px;
  position: absolute;
  top: 0;
  background: linear-gradient(0deg, rgba(255, 255, 255, 0.00) 0%, #FFF 50%);
}

.play-guide-card-wrapper-b {
  display: flex;
  height: 560px;
  flex-direction: column;
  justify-content: flex-end;
  align-items: center;
  flex: 1 0 0;
  border-radius: 16px;
  background: #FFF;
  box-shadow: 0 4px 8px 0 rgba(218, 224, 230, 0.38);
  overflow: hidden;
  position: relative;
}

.play-guide-card-img-wrapper-b {
  display: flex;
  justify-content: center;
  height: 100%;
  box-shadow: 0 8px 16px 0 rgba(218, 224, 230, 0.75);
  border-radius: 12px;
}

.play-guide-card-img-wrapper-b.card-3 {
  background: url("https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/play-guide-step-3.png") no-repeat center center;
  background-size: cover;
  width: 240px;
  min-height: 480px;
  margin-bottom: 24px;
}

.play-guide-card-img-wrapper-b.card-4 {
  background: url("https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/play-guide-step-4-1.png") no-repeat center center;
  background-size: contain;
  display: flex;
  width: 400px;
  height: 320px;
  flex-direction: column;
  align-items: flex-start;
  flex: 1 0 0;
  margin: 60px 0;
}
.play-guide-text-wrapper-b {
  display: flex;
  padding: 0 40px 48px 40px;
  flex-direction: column;
  align-items: flex-start;
  align-self: stretch;
}

.play-guide-start-wrapper {
  display: flex;
  padding: 40px 0;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  align-self: stretch;
  gap: 24px;
  border-radius: 20px;
  background: linear-gradient(94deg, #8C33E5 25%, #4E1C80 100%);
  box-shadow: 0 8px 16px 0 #DAE0E6;
}

.play-guide-start-h2 {
  color: #FFF;
  text-align: center;
  font-size: 20px;
  font-style: normal;
  font-weight: 700;
  line-height: 28px;
}

.play-guide-start-btn {
  display: flex;
  padding: 10px 16px 12px 16px;
  align-items: flex-start;
  border-radius: 100px;
  border: 2px solid rgba(255, 255, 255, 0.75);
  background: rgba(205, 175, 255, 0.25);
  color: #FFF;
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: 24px;
  transition: all 0.2s ease-in-out;
}

.play-guide-start-btn:hover {
  border: 2px solid rgba(139, 70, 255, 0.25);
  background: #8B46FF;
}

@media (max-width: 991px) and (min-width: 768px) {
  .play-guide-section {
    padding: 80px 0;
  }

  .play-guide-card-h3 {
    font-size: 15px;
  }
}

@media (max-width: 767px) {
  .play-guide-section {
    padding: 80px 0;
  }

  .play-guide-card-line-wrapper {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 24px;
    align-items: stretch;
  }

  .play-guide-p {
    font-size: 16px;
  }

  .play-guide-card-wrapper,
  .play-guide-card-wrapper-b {
    flex: 1 0 auto;
  }

  .play-guide-card-wrapper-b {
    flex-direction: column-reverse;
    padding: 20px 24px 0 24px;
  }

  .play-guide-text-wrapper-b {
    padding: 0 0 20px 0;
  }

  .play-guide-text-wrapper {
    padding: 20px 24px 0 24px;
  }

  .play-guide-card-h3 {
    font-size: 15px;
  }

  .play-guide-card-p {
    font-size: 14px;
    line-height: 20px;
  }

  .blur-wrapper {
    height: 40px;
    position: absolute;
    top: 0;
    background: linear-gradient(0deg, rgba(255, 255, 255, 0.00) 0%, #FFF 50%);
  }

  .play-guide-card-img-wrapper.card-1 img {
    display: none;
  }

  .play-guide-card-wrapper.card-2 {
    height: auto;
  }

  .play-guide-card-img-wrapper.card-2 {
    position: inherit;
    background: none;
    width: 100%;
    aspect-ratio: 1 / 1;
    flex: 1 1 100%;
  }

  .play-guide-card-img-wrapper.card-2 img {
    width: 100%;
    aspect-ratio: 1 / 1;
    position: inherit;
  }

  .play-guide-card-img-wrapper-b.card-3 {
    position: inherit;
    background: none;
    width: 100%;
    aspect-ratio: 2 / 1;
    flex: 1 1 100%;
    margin: 0 0 24px 0;
    box-shadow: inherit;
  }

  .play-guide-card-img-wrapper-b.card-3 img {
    width: 100%;
    aspect-ratio: 2 / 1;
    position: inherit;
  }

  .play-guide-card-wrapper-b.card-3, .play-guide-card-wrapper-b.card-4 {
    height: auto;
  }

  .play-guide-card-img-wrapper-b.card-3, .play-guide-card-img-wrapper-b.card-4 {
    position: relative;
    background: none;
    width: 100%;
    aspect-ratio: 5 / 4;
    flex: 1 1 100%;
    box-shadow: inherit;
    max-width: 240px;
  }

  .play-guide-card-img-wrapper-b.card-4 {
    margin: 0;
  }

   .play-guide-card-img-wrapper-b.card-4 img {
    width: 100%;
    aspect-ratio: 5 / 4;
    position: inherit;
  }

  .play-guide-h1 {
    font-size: 32px;
  }
}
</style>