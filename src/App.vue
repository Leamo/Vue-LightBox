<template>
  <div id="app">
    <section>
      <a :href="'https://picsum.photos/800/600?image=' + 1+n" v-lightbox v-for="n in 9" :key="n">
        <img :src="'https://picsum.photos/150?image=' + 1+n">
      </a>
    </section>
    <br/>
    <section>
      <a :href="'https://picsum.photos/800/600?image=' + 4+n" v-lightbox="'grouptest'" v-for="n in 9" :key="n">
        <img :src="'https://picsum.photos/150?image=' + 4+n">
      </a>
    </section>
    <lightbox></lightbox>
  </div>
</template>

<script>
import Lightbox from './components/lightbox/Lightbox.vue'

export default {
  name: 'app',
  components: {
    Lightbox
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
