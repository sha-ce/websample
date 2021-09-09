<template>
  <div>
    <!-- ハンバーガーメニューのボタン -->
    <div class="button" :class="{'close-button':ActiveBtn}" @click="ActiveBtn=!ActiveBtn">
      <span class="icon-bar line-1" :class="{'close-1':ActiveBtn}"></span>
      <span class="icon-bar line-2" :class="{'close-2':ActiveBtn}"></span>
      <span class="icon-bar line-3" :class="{'close-3':ActiveBtn}"></span>
    </div>
    <!-- サイドメニュー -->
    <transition name="fade">
      <div v-if="ActiveBtn" class="nav-content">
          <ul>
            <li>
              <div class="home">
                <a href="/">
                  <font-awesome-icon class="icon" icon="home" />
                  C3について
                </a>
              </div>
            </li>
            <li><p>コミュニティ</p></li>
            <li>
              <div class="list">
                <a href="#GAME">
                  <font-awesome-icon class="icon" icon="gamepad" />
                  GAME
                </a>
              </div>
            </li>
            <li>
              <div class="list">
                <a href="#CG">
                  <font-awesome-icon class="icon" :icon="['far', 'images']" />
                  CG
                </a>
              </div>
            </li>
            <li>
              <div class="list">
                <a href="#HACK">
                  <font-awesome-icon class="icon" icon="laptop-code" />
                  HACK
                </a>
              </div>
            </li>
            <li>
              <div class="list">
                <a href="#MEDIA">
                  <font-awesome-icon class="icon" icon="palette" />
                  MEDIA_ART
                </a>
              </div>
            </li>
            <li>
              <div class="home">
                <a href="#news">
                  <font-awesome-icon class="icon" icon="home" />
                  お知らせ
                </a>
              </div>
            </li>
            <li>
              <div class="home">
                <a href="#blog">
                  <font-awesome-icon class="icon" icon="home" />
                  ブログ
                </a>
              </div>
            </li>
          </ul>
        </div>
    </transition>
    <div v-if="ActiveBtn" class="close-area" @click="ActiveBtn=!ActiveBtn"/>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ActiveBtn: false,
      linkUrl1: "#",
      linkUrl2: "#",
      linkUrl3: "#",
      linkUrl4: "#"
    }
  }
};
</script>

<style scoped>
p {
  margin: 0;
  padding: 0;
}
.button {
  position: fixed;
  cursor: pointer;
  z-index: 100;
  padding: 10px;
  transition: 0.5s ease;
}
.icon-bar {
  display: block;
  width: max(4vh, 20px);
  height: 2px;
  background: gray;
}
.icon-bar + .icon-bar {
  margin-top: 8px;
}
.line-1, .line-2, .line-3 {
  transition: 0.5s ease;
}

/* ボタンアニメーション */
.close-1 {
  transform: translate3d(0, 10px, 0) rotate(-45deg);
  transition: 0.5s ease;
}
.close-2 {
  transition: 0.5s ease;
  opacity: 0;
}
.close-3 {
  transform: translate3d(0, -10px, 0) rotate(45deg);
  transition: 0.5s ease;
}
.close-button {
  background: #efefef;
  border-radius: 10px/10px;
  position: fixed;
  left: 10px;
  transition: 0.5s ease;
  box-shadow: 0 1px 3px 2px #dfdfdf;
}
/* ↑ボタンアニメーション */

.nav-content {
  margin: 0;
  padding: 10px 0 0 40px;
  position: fixed;
  top: 90px;
  left: 10px;
  /*height: 60%;*/
  display: inherit;
  background: #efefef;
  pointer-events: auto;
  flex-direction: column;
  border-radius: 20px/20px;
  box-shadow: 0 1px 3px 2px #dfdfdf;
  z-index: 99;
}
.fade-enter-active, .fade-leave-active {
  opacity: 1;
  transition: 0.5s ease;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
  transition: 0.5s ease;
}
.home {
  margin: 10px 0;
}
.list {
  padding-left: 20px;
}
.home,
.list {
  display: flex;
}
.icon {
  color: #303030;
  font-size: 15px;
}
.nav-content li a,
.nav-content li p {
  padding: 5px 5px;
  display: block;
  text-transform: uppercase;
  transition: color 0.1s;
  color: #303030;
  font-size: max(5%, 20px);
}

.nav-content li a:hover {
  opacity: 0.6;
  color: #aa0000;
}
.nav-container:focus-within .nav-content {
  transform: none;
}
a,
a:visited,
a:focus,
a:active,
a:link {
  text-decoration: none;
  outline: 0;
}
a {
  color: currentColor;
  transition: 0.2s ease-in-out;
}
ul {
  padding: 0;
  list-style: none;
}
.close-area {
  position: fixed;
  width: 100%;
  height: 100%;
}
/* スマホ以上 */
@media screen and (min-width: 481px) {
  .button {
    top: 20px;
    left: 20px;
  }
  .nav-content {
    width: 300px;
  }
}
/* スマホ幅 */
@media screen and (max-width: 480px) {
  .button {
    top: 10px;
    left: 10px;
  }
  .nav-content {
    width: 80%;
  }
}
</style>
