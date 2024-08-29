<script setup>
const redirectToPage = (url) => {
  window.location.href = url
}

const triggerDivClick = () => {
  // 특정 div 요소를 찾음
  const targetDiv = document.querySelector('div[data-ch-testid="launcher"]');

  // 요소가 존재하면 클릭 이벤트를 트리거
  if (targetDiv) {
    targetDiv.click();
  } else {
    console.error('Target div not found');
  }
};
</script>

<template>
  <section class="footer-section">
    <div class="footer-wrapper scroll-horizontal-action">
      <h4 class="footer-h4">플레이 등록 방법이 궁금하신가요?</h4>
      <h2 class="footer-h2">플레이매니저와 상담하고 <br>
        빠르게 플레이를 등록하세요. </h2>
      <button @click="triggerDivClick" class="footer-btn">지금 플레이 시작하기</button>
    </div>
  </section>
</template>

<style scoped>
.scroll-horizontal-action {
  opacity: 0;
  transform: translateY(40px);
  transition: all 0.7s ease-out;
}

.scroll-horizontal-action.show {
  opacity: 1;
  transform: translateY(0);
}

.footer-section {
  width: 100%;
  margin: auto;
  padding: 120px 16px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #FFF;
}

.footer-wrapper {
  display: flex;
  width: 1140px;
  max-width: 1140px;
  height: auto;
  padding: 64px 0;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 12px;
  background-image: url("https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/bottom-banner.png");
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  border-radius: 40px;
}

.footer-h4 {
  color: #FFF;
  text-align: center;
  font-size: 20px;
  font-style: normal;
  font-weight: 700;
  line-height: 28px;
}

.footer-h2 {
  color: #FFF;
  text-align: center;
  font-size: 36px;
  font-style: normal;
  font-weight: 700;
  line-height: 150%;
  margin-bottom: 20px;
}

.footer-btn {
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px 16px 12px 16px;
  border-radius: 100px;
  border: 2px solid rgba(255, 255, 255, 0.75);
  background: rgba(205, 175, 255, 0.25);
  transition: all 0.2s ease-in-out;
  color: #FFF;
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: 24px;

}

.footer-btn:hover {
  border: 2px solid rgba(139, 70, 255, 0.25);
  background: #8B46FF;
}

@media (max-width: 991px) and (min-width: 768px) {
  .footer-section {
    padding: 120px 16px;
  }
}

@media (max-width: 767px) {

  .footer-section {
    padding: 80px 16px;
  }

  .footer-h4 {
    font-size: 12px;
  }

  .footer-h2 {
    font-size: 20px;
  }
}
</style>