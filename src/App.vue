<template>
  <div id="app">
      <Header />
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
export default {
  name: 'App',
  components: {
    Header,
  },
}
</script>

<style lang="scss">
@import '@/styles/globals.scss';
@import '@/styles/vars.scss';

#app {
    height: 100vh;
    width: 100vw;
}
</style>


// https://flynn.boolean.careers/exercises/api/array/music