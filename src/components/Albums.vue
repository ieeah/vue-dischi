<template>
    <div class="albums_container">
        <Albumcard v-for="(album, i) in storedAlbums" :key="`album_${i}`"
            :poster="album.poster" :title="album.title" :subTitle="album.author" :year="album.year" :genre="album.genre"
        />
    </div>
</template>

<script>
import Albumcard from '@/components/Albumcard.vue';
import axios from 'axios';
export default {
    name: 'Albums',
    components: {
        Albumcard,
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
            axios.get('https://flynn.boolean.careers/exercises/api/array/music').then( response => {
                this.storedAlbums = response.data.response;
            });
        },
    },
}
</script>
<style scoped lang="scss">

.albums_container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    padding: 110px 70px;
}

</style>