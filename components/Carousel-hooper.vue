<template>
  <div class="carousel-wrap">
    <div class="carousel-outer">
      <hooper :settings="hooperSettings">
        <slide 
          v-for="(slide, idx) in slides"
          :key="idx"
          class="carousel-inner"
        >
          <img :src="slides[idx].img"/>
        </slide>
        <hooper-navigation slot="hooper-addons" class="carousel-dots"></hooper-navigation>
        <hooper-pagination slot="hooper-addons"></hooper-pagination>
      </hooper>
      <div class="button-wrap">
      </div>
    </div>
  </div>
</template>

<script>
import { 
  Hooper,
  Slide,
  Pagination as HooperPagination,
  Navigation as HooperNavigation
} from 'hooper';
import 'hooper/dist/hooper.css'

export default {
  components: { 
    Hooper,
    Slide,
    HooperPagination,
    HooperNavigation
  },
  data() {
    return {
      slides: [
        { img: '/carousel_1.png' },
        { img: '/carousel_2.png' },
        { img: '/carousel_3.png' },
        { img: '/carousel_4.png' },
        { img: '/carousel_5.png' }
      ],
      hooperSettings: {
        infiniteScroll: true,
        centerMode: true,
        keysControl: false,
        autoPlay: true,
        playSpeed: 4000,
        transition: 800
      }
    }
  }
};
</script>

<style scoped>
.carousel-wrap {
  margin: 0;
  padding: 40px 0;
  width: 100%;
}
.carousel-outer {
  width: 350px;
  height: 200px;
  margin: 0 auto;
  text-align: center;
  background: white;
}
.carousel-inner-wrap {
  white-space: nowrap;
}
.carousel-inner {
  position: relative;
  width: 350px;
  height: 200px;
  display: inline-block;
}
.carousel-inner img {
  width: 350px;
  height: 200px;
  border-radius: 30px;
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
</style>
