<template>
  <div class="container">
    <Header/>
    <Menu/>
    <TopTop/>
    <Carouselhooper/>
    <Main/>
    <Footer/>
  </div>
</template>

<script>
import Menu from '../components/Menu.vue';
import Header from '../components/Header.vue';
import TopTop from '../components/topTop.vue';
import Main from '../components/Main.vue';
import Footer from '../components/Footer.vue';
import Carouselhooper from '../components/Carousel-hooper.vue';

export default {
  components: { Header, Menu, TopTop, Main, Footer, Carouselhooper },
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
  }
</style>
