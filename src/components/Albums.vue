<template>
    <div v-if="storedAlbums" class="albums_container">
        <Albumcard v-for="(album, i) in storedAlbums" :key="`album_${i}`"
            :poster="album.poster" :title="album.title" :subTitle="album.author" :year="album.year" :genre="album.genre"
        />
    </div>
    <Loader v-else />
</template>

<script>
import Albumcard from '@/components/Albumcard.vue';
import Loader from '@/components/Loader.vue';
import axios from 'axios';
export default {
    name: 'Albums',
    components: {
        Albumcard,
        Loader,
    },
    data() {
        return {
            storedAlbums: null,
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
    },
}
</script>
<style scoped lang="scss">
@import '@/styles/globals.scss';
.albums_container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    padding: 110px 70px;
}

</style>