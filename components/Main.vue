<template>
  <div class="wrap">
    <div class="title">
      nuxt.js
    </div>
    <div>
      <p>window width : {{ width }}</p>
      <p v-if="width < 768">is smartphone view</p>
      <p v-else>is PC view</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      width: window.innerWidth,
    }
  },
  methods: {
    // 無くても良いが lodash の debounce で発火頻度を調整してあげるとエコ
    setWindowWidth() {
      // data にリサイズ後のウィンドウ幅を代入
      this.width = window.innerWidth;
    },
  },
}
</script>


<style scoped>
.wrap {
  margin: 0;
  padding: 0;
  width: 100%;
  background: ghostwhite;
}
.title {
  font-size: max(32px, 20vw);
  color: gray;
  height: 100vh;
  /* 中央寄せ */
  display: -webkit-flex;
  display: flex;
  -webkit-align-items: center; /* 縦方向中央揃え（Safari用） */
  align-items: center; /* 縦方向中央揃え */
  -webkit-justify-content: center; /* 横方向中央揃え（Safari用） */
  justify-content: center; /* 横方向中央揃え */
}
</style>
