<template>
  <div>
    <div class="wrap">
      <div class="left-wrap">
        <div class="top-title">
          <div class="top-title-text"><div class="top-title-text-c">C</div>omposite</div>
          <div class="top-title-text"><div class="top-title-text-c">C</div>omputer</div>
          <div class="top-title-text"><div class="top-title-text-c">C</div>lub</div>
        </div>
        <div class="top-news-nav">
          <div class="top-news-flex-wrap">
            <div class="top-news-title">
              お知らせ
            </div>
            <div class="all-news-link">
              <a href="#allnews">一覧を見る</a>
            </div>
          </div>
          <div class="top-news">
            <a href="#topnews">
              {{ news }}
            </a>
          </div>
        </div>
      </div>
      <div class="right-wrap">
        <div class="carousel-nav">
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
      news: '2021.9.30　オフィシャルサイト更新！！',
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
};
</script>

<style scoped>
.wrap {
  margin: 0;
  padding: 80px/*ヘッダーの高さ*/ 0 50px 0;
  background: white;
  color: gray;
  display: flex;
  height: cal(100vh - 80px/* ヘッダーの高さ */);
  font-family: 'Inter';
}
/* タイトル */
.top-title {
  margin: 0;
  padding: min(50px, 4vw) min(40px, 3.8vw) min(120px, 6.5vw) min(100px, 5.3vw);
}
.top-title-text {
  font-size: min(120px, 8vw);
  display: inherit;
  display: flex;
}
.top-title-text-c {
  color: #ddddff;
  display: inline;
}
/* お知らせ */
.top-news-nav {
  margin: 0;
  padding: min(40px, 4vw) min(40px, 3.8vw) min(20px, 2vw) min(70px, 4.5vw);
  box-shadow: 1px 1px 5px 2px lightgray;
  border-radius: 0 20px 20px 0;
}
.top-news-flex-wrap {
  display: flex;
  vertical-align: middle;
}
.top-news-title {
  margin: 0;
  padding: 0;
  width: 70%;
  font-size: min(30px, 3.5vw);
}
.all-news-link {
  font-size: min(25px, 2.5vw);
  text-align: right;
}
.all-news-link a {
  color: gray;
}
.top-news {
  margin: 0;
  padding: min(50px, 4vw) min(30px, 1.5vw);
  font-size: min(23px, 2.5vw);
}
.top-news a {
  margin: 0;
  padding: min(20px, 2vw) min(40px, 3.8vw);
  text-decoration: none;
  color: gray;
  border: solid gray;
  border-width: 0.1vw;
  border-radius: 50px;
  display: inline;
  white-space: nowrap;
}
.top-news a:hover, .all-news-link a:hover {
  opacity: 0.5;
  transition: 0.3s ease;
}
/* カルーセル */
.carousel-nav {
  margin: min(50px, 4vw) min(100px, 5.3vw) min(100px, 5.3vw) min(100px, 5.3vw);
  background: gray;
  width: min(900px, 47vw);
  height: min(700px, 37vw);
  border-radius: 25px/25px;
  box-shadow: 8px 6px 6px lightgray;
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
  margin: 0;
  padding: 0;
  width: min(900px, 47vw);
  height: min(700px, 37vw);
  border-radius: 25px/25px;
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
