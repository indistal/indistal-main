<template>
  <div class="modal-overlay" @click.self="closeModal">
    <div class="modal-container">
      <div class="modal-header">
        <div class="modal-title-wrapper">
          <img class="naver-logo" v-if="props.contentType === '여행기/탐방기'" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/naver-influencer-logo.png"/>
          <img class="youtube-logo" v-if="props.contentType === '웹예능' || props.contentType === '숏폼' || props.contentType === '스케치 코미디' || props.contentType === '커머스'" src="https://cdn.jsdelivr.net/gh/INC-THECOMPASS/indistal_report_build@main/main_dist/assets/images/youtube-logo-black.png"/>
          <span class="modal-title">X {{ modalTitle }}</span>
        </div>
        <button class="modal-close-btn" @click="closeModal">×</button>
      </div>
      <div class="modal-body-content">
        <iframe v-if="props.contentType === '여행기/탐방기'" src="https://m.blog.naver.com/PostView.naver?blogId=jeongyonghan&logNo=223540462111&proxyReferer=&noTrackingCode=true" :width="props.isMobile ? 344 : 396" height="400"></iframe>
        <iframe v-if="props.contentType === '웹예능'" :width="props.isMobile ? 350 : 400" height="400" src="https://www.youtube.com/embed/5-tEGTM5ODQ?si=S946yrl2indfS-RQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe v-if="props.contentType === '숏폼'" :width="props.isMobile ? 350 : 400" height="400" src="https://www.youtube.com/embed/zxwNib2E2bE" title="Top7에게 도전장 내미는 마술사 ㅋㅋ #인디스탈" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe v-if="props.contentType === '스케치 코미디'" :width="props.isMobile ? 350 : 400" height="400" src="https://www.youtube.com/embed/KkYYXV-8xNE" title="위험한 초대" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        <iframe v-if="props.contentType === '커머스'" :width="props.isMobile ? 350 : 400" height="400" src="https://www.youtube.com/embed/uuEKd33g_IE?start=167" title="오늘부터 우리는 1일❤️ / 호텔 가자마자...?! / 수영장에서 생긴 일🫣[자기야~ 어때?] ep.01" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed, defineEmits } from 'vue'

const props = defineProps(['contentType', 'isMobile'])
const emit = defineEmits(['close']);

const modalTitle = computed(() => {
  if (props.contentType === '여행기/탐방기')  return '블로그';
  if (props.contentType === '숏폼') return '숏폼';
  if (props.contentType === '웹예능' ) return '웹예능';
  if (props.contentType === '스케치 코미디')  return '스케치코미디'
  if (props.contentType === '커머스')  return '커머스';
})

const closeModal = () => {
  emit('close');
};
</script>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1499;
}

.modal-container {
  background: white;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  display: flex;
  flex-direction: column;
  z-index: 1500;
}

.modal-body-content {
  width: 400px;
  height: 400px;
}

.modal-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px;
  border-bottom: 1px solid #ddd;
}

.modal-title-wrapper {
  display: flex;
  align-items: center;
  gap: 6px;
}

.naver-logo {
  width: 27px;
  height: 26px;
}

.youtube-logo {
  width: 76px;
  height: 16px;
}

.instagram-logo {
  width: 20.005px;
  height: 20px;
}

.modal-title {
  color: #12161A;
  font-size: 16px;
  font-style: normal;
  font-weight: 700;
  line-height: 24px;
}

.modal-close-btn {
  border: none;
  background: none;
  font-size: 20px;
  cursor: pointer;
}

@media (max-width: 767px) {
  .modal-body-content {
    width: 350px;
    height: 350px;
  }
}
</style>
