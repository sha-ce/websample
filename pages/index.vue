<template>
  <div class="container">
    <Header/>
    <Menu/>
  </div>
</template>

<script>
import Menu from '../components/Menu.vue';
import Header from '../components/Header.vue';

export default {
  components: { Header, Menu },
}
</script>

<style scoped>
  html, body {
    margin: 0;
    padding: 0;
  }
</style>
