<template>
  <div class="container">
    <Header/>
    <Menu/>
    <Main/>
    <Footer/>
  </div>
</template>

<script>
import Menu from '../components/Menu.vue';
import Header from '../components/Header.vue';
import Main from '../components/Main.vue';
import Footer from '../components/Footer.vue';

export default {
  components: { Header, Menu, Main, Footer },
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
  }
</style>
