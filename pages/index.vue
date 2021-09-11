<template>
  <div class="container">
    <Header/>
    <Menu/>
    <TopTop/>
    <Carousel/>
    <Main/>
    <Footer/>
  </div>
</template>

<script>
import Menu from '../components/Menu.vue';
import Header from '../components/Header.vue';
import Main from '../components/Main.vue';
import Footer from '../components/Footer.vue';
import TopTop from '../components/topTop.vue';
import Carousel from '../components/Carousel-sample.vue';

export default {
  components: { Header, Menu, Main, Footer, TopTop, Carousel },
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
  }
</style>
