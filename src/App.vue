<template>
    <div id="app">
        <Header @genResearch="test" />
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
    props: {
},
data() {
    return {
        storedAlbums: [],
        selectedAlbums: [],
        text: 'All',
    };
    },
    created() {
        this.getAlbums();
    },
    computed: {
        albumsToShow() {
        if(this.text === 'All') {
            return this.storedAlbums;
        }

        return this.storedAlbums.filter(album => album.genre === this.text);
        }
    },
    methods: {

        getAlbums() {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music').then(received => {
                this.storedAlbums = received.data.response;
            });
        },

        test(selectedGenre) {
            this.text = selectedGenre;
        },
    },
}
</script>

<style lang="scss">
@import '@/styles/globals.scss';
@import '@/styles/vars.scss';

</style>
