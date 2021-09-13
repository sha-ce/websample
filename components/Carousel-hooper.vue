<template>
  <div class="carousel-wrap">
    <div class="carousel-outer">
      <hooper :settings="hooperSettings">
        <slide 
          v-for="(slide, idx) in slides"
          :key="idx"
          class="carousel-inner"
        >
          <a :href="links[idx].src" >
            <img :src="slides[idx].img"/>
          </a>
        </slide>
        <hooper-navigation slot="hooper-addons"></hooper-navigation>
        <hooper-pagination slot="hooper-addons"></hooper-pagination>
      </hooper>
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
      links: [
        { src: '#1' },
        { src: '#2' },
        { src: '#3' },
        { src: '#4' },
        { src: '#5' },
      ],
      hooperSettings: {
        infiniteScroll: true,
        centerMode: true,
        keysControl: false,
        autoPlay: true,
        playSpeed: 5000,
        transition: 800
      },
    }
  },
  methods: {
    /* */
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
  width: min(900px, 47vw);
  height: min(700px, 37vw);
  border-radius: 25px/25px;
  box-shadow: 8px 6px 6px lightgray;
  margin: 0 auto;
  text-align: center;
  background: white;
}
.carousel-inner {
  position: relative;
  width: min(900px, 47vw);
  height: min(700px, 37vw);
  display: inline-block;
}
.carousel-inner img {
  width: min(900px, 47vw);
  height: min(700px, 37vw);
  border-radius: 25px/25px;
  border: solid 1px rgb(200, 200, 255);
  object-fit: cover;
}
</style>

<style>/* scopedされてないけどそうじゃないとデフォルトのままなんだ */
.hooper {
  width: 900px;
  height: 700px;
}
.hooper-list {
  border-radius: 25px/25px;
}
.hooper-pagination {
  bottom: -30px;
}
.hooper-indicator {
  margin: 0 20px;
  padding: 0;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: gray;
  opacity: 0.3;
}
.hooper-indicator:hover, .hooper-indicator .is-active {
  background: gray;
  opacity: 0.6;
  transition: 0.3s ease;
}
.hooper-indicator.is-active {
  background: gray;
  opacity: 0.9;
}
.hooper-next, .hooper-prev {
  margin: 10px;
  padding: 5px;
  background: lightgray;
  opacity: 0.2;
  border-radius: 50%;
}
.hooper-next:hover, .hooper-prev:hover {
  margin: 10px;
  background: lightgray;
  opacity: 0.5;
  border-radius: 50%;
  transition: 0.3s ease;
}
</style>
