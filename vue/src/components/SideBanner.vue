<template>
  <div class="side-banner" :class="{ 'banner-hidden': !isBannerVisible }">
    <div class="banner-content">
      <h5 class="banner-title">사이드배너</h5>
      <p class="banner-text">만점.</p>
      <a href="#" class="banner-link" @click="toggleBanner">배너 {{ isBannerVisible ? '닫기' : '열기' }}</a>
    </div>
    <div class="banner-overlay" @click="toggleBanner" v-if="!isBannerVisible"></div>
  </div>
</template>

<script>
export default {
  name: 'SideBanner',
  data() {
    return {
      isBannerVisible: true // 배너의 초기 상태는 보이는 상태
    }
  },
  methods: {
    toggleBanner() {
      this.isBannerVisible = !this.isBannerVisible; // 배너의 상태를 토글
    }
  }
}
</script>

<style scoped>
.side-banner {
  background-color: rgb(170, 170, 240);
  padding: 10px;
  display: flex;
  align-items: center;
  position: fixed; /* 배너의 위치를 고정 */
  top: 50%; /* 원하는 위치로 조정 */
  transform: translateY(-50%); /* 수직 가운데 정렬 */
  text-align: center; /* 버튼을 중앙 정렬 */
  z-index: 500;
  margin-left: 5px;
  border-radius: 20px;
  width: 100px;
  height: 150px;
  overflow: hidden;
  transition: margin-left 0.3s; /* 애니메이션을 위한 트랜지션 설정 */
}

.banner-content {
  flex: 1;
}

.banner-title {
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 5px;
}

.banner-text {
  font-size: 14px;
  color: #000;
  margin-bottom: 10px;
  font-weight: bold;
}

.banner-link {
  display: inline-block;
  padding: 5px 10px;
  background-color: #007bff;
  color: #fff;
  font-size: 14px;
  text-decoration: none;
  border-radius: 4px;
}

.banner-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 9998;
  background-color: rgb(170, 170, 240);
}

.banner-hidden {
  margin-left: -80px; /* 숨겨진 상태에서의 왼쪽 마진 설정 */
}
</style>
