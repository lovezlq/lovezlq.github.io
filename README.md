<template>
  <!-- 微信/QQ环境显示引导层 -->
  <div v-if="showGuide" class="guide-layer">
    <button @click="handleJump">点击跳转浏览器</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showGuide: /MicroMessenger|QQ\//i.test(navigator.userAgent) ‌:ml-citation{ref="1,2" data="citationList"}
    }
  },
  methods: {
    handleJump() {
      // 跳转中间页或直接地址
      window.location.href = 'https://c.pc.qq.com/middle.html?pfurl=' + 
        encodeURIComponent(encodeURIComponent(window.location.href)) ‌:ml-citation{ref="1,2" data="citationList"}
    }
  }
}
</script>

<style>
.guide-layer {
  position: fixed;
  background: rgba(0,0,0,0.9);
  z-index: 9999;
}
</style>
