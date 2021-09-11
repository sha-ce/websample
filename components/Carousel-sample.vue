<template>
  <div class="carousel-wrap">
    <div class="carousel-outer">
      <ul class="carousel-inner">
        <li>
          <transition :name="transName">
          <img 
            v-for="(slide, index) in slides"
            v-show="currentSlide == index"
            :key="index"
            :src="slides[index].img"
          />
          </transition>
        </li>
      </ul>
      <div class="button-wrap">
        <button class="button button-prev" @click="prev()">＜</button>
        <button class="button button-next" @click="next()">＞</button>
      </div>
    </div>
    <div class="carousel-dots-wrap">
      <div class="carousel-dots">
        <ul>
          <li 
            v-for="(slide, index) in slides"
            :key="index"
            >
            <button
              :class="{ 'carousel-dot-active': currentSlide == index }"
              class="carousel-dot"
              @click="currentSlide = index"
            />
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      transName: null,
      currentSlide: 0,
      slides: [
        { img: '/carousel_1.png' },
        { img: '/carousel_2.png' },
        { img: '/carousel_3.png' },
        { img: '/carousel_4.png' },
        { img: '/carousel_5.png' }
      ],
    }
  },
  methods: {
    prev() {
      this.transName = 'prev'
      this.currentSlide--
      if (this.currentSlide === -1) {
        this.currentSlide = this.slides.length - 1
      }
    },
    next() {
      this.transName = 'next'
      this.currentSlide++
      if (this.currentSlide === this.slides.length) {
        this.currentSlide = 0
      }
    },
  },
}
</script>


<style scoped>
.carousel-wrap {
  margin: 0;
  padding: 40px 0;
  width: 100%;
}
.carousel-outer {
  width: 550px;
  height: 300px;
  margin: 0 auto;
  text-align: center;
  background: white;
}
.carousel-inner {
  white-space: nowrap;
}
.carousel-inner li {
  display: inline-block;
}
.carousel-inner li img {
  width: 550px;
  height: 300px;
  border-radius: 50px;
  border: solid 1px rgb(200, 200, 255);
}
.carousel-dots-wrap {
  width: 100%;
  height: auto;
}
.carousel-dots ul {
  width: 150px;
  margin: 0 auto;
  padding: 0 auto;
  display: flex;
}
.carousel-dots li {
  list-style: none;
}
.carousel-dot {
  margin: 0 10px;
  padding: 0;
  width: 10px;
  height: 10px;
  cursor: pointer;
  border-radius: 50%;
  background: gray;
  display: inline-flex;
  opacity: 0.3;
  border: none;
}
.carousel-dot-active {
  opacity: 0.8;
}
.button-wrap {
  text-align: center;
  position: absolute;
  left: 36.7%;
  bottom: -230px;
}
.button {
  cursor: pointer;
  width: 50px;
  height: 50px;
  font-size: 30px;
  color: white;
  border: none;
  border-radius: 50%;
  background: gray;
  opacity: 0.2;
}
.button-prev {
  margin: 0 200px 0 0;
  text-align: left;
}
.button-next {
  margin: 0 0 0 200px;
  text-align: right;
}
/* -------------------------------- */
/* 以下 Vue.js で使用するクラスの定義 */
/* -------------------------------- */
.next-enter, .prev-leave-to {
  transition: 0.5s ease;
  transform: translateX(550px);
}
.next-leave-to, .prev-enter {
  transition: 0.5s ease;
  transform: translateX(-550px);
}
</style>
