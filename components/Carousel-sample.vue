<template>
  <div class="carousel-wrap">
    <div class="carousel-outer">
      <transition-group 
        :name="transName" 
        class="carousel-inner-wrap"
        tag="ul"
      >
        <li 
          v-for="(slide, idx) in slides"
          v-show="currentSlide == idx"
          :key="idx"
          class="carousel-inner"
        >
          <img 
            :src="slides[idx].img"
          />
        </li>
      </transition-group>
      <div class="button-wrap">
        <button class="button button-prev" @click="prev(1)">＜</button>
        <button class="button button-next" @click="next(1)">＞</button>
      </div>
    </div>
    <div class="carousel-dots-wrap">
      <div class="carousel-dots">
        <ul>
          <li 
            v-for="(slide, idx) in slides"
            :key="idx"
            >
            <button
              :class="{ 'carousel-dot-active': currentSlide == idx }"
              class="carousel-dot"
              @click="animation(idx)"
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
      prevSlide: 4,
      currentSlide: 0,
      nextSlide: 1,
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
    prev(decre) {
      this.transName = 'prev'
      this.currentSlide-=decre
      if (this.currentSlide === -1) {
        this.prevSlide = 3
        this.currentSlide = 4
        this.nextSlide = 0
      }
    },
    next(incre) {
      this.transName = 'next'
      this.currentSlide+=incre
      if (this.currentSlide === 5) {
        this.prevSlide = 4
        this.currentSlide = 0
        this.nextSlide = 1
      }
    },
    animation(idx) {
      if(idx >= this.currentSlide) {
        return this.next(idx - this.currentSlide)
      } else {
        return this.prev(this.currentslide - idx)
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
.carousel-inner-wrap {
  white-space: nowrap;
}
.carousel-inner {
  width: 550px;
  height: 300px;
  display: inline-block;
}
.carousel-inner img {
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
.next-enter-active,
.next-leave-active,
.prev-enter-active,
.prev-leave-active {
  transition: all 0.8s ease;
}
.next-leave-to {
  transform: translatex(-100%);
}
.next-enter {
  transform: translateX(100%);
}
.next-enter-active {
  transform: translateX(-100%);
}
.prev-enter {
  transform: translateX(100%);
}
.prev-leave-active {
  transform: translateX(0);
}
.prev-enter-to {
  transform: translateX(0);
}

</style>
