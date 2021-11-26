<template>
  <div id="app">
      <Header @genResearch="filterAlbums" />
      <Albums :albums="albumsToShow"/>
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Albums from '@/components/Albums.vue';
import axios from 'axios';
export default {
  name: 'App',
  components: {
    Header,
    Albums,
  },
  data() {
    return {
      storedAlbums: '',
      albumsToShow: '',
    };
  },
  created() {
        this.getAlbums();
    },
    methods: {

        getAlbums() {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music').then(received => {
                this.storedAlbums = received.data.response;
            });
        },

        filterAlbums(selectedGenre) {
          if(selectedGenre === '') {
            this.albumsToShow = this.storedAlbums;
          } else {
            this.albumsToShow = this.storedAlbums.filter(album => album.genre === selectedGenre);
          }
        },
    },
}
</script>

<style lang="scss">
@import '@/styles/globals.scss';
@import '@/styles/vars.scss';

</style>
