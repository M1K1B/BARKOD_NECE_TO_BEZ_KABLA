<template>
  <Konvertor class="mb-3" />
  <div class="row mx-auto col-12">
    <Kvote class="mb-3" />
    <div class="col-12 col-md-1"></div>
    <Graf class="mb-3" />
  </div>
</template>

<script>
import Konvertor from './components/Konvertor.vue'
import Kvote from './components/Kvote.vue'
import Graf from './components/Graf.vue'

export default {
  name: 'App',
  components: {
    Konvertor,
    Kvote,
    Graf
  }
}
</script>

<style>
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: white;
  margin: 0;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
}
</style>
