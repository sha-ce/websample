<template>
  <div class="wrap">
    <div class="title">
      nuxt.js
    </div>
  </div>
</template>

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
