<template>
    <div v-if="albums.length > 0" class="albums_container">
        <Albumcard v-for="(album, i) in albums" :key="`album_${i}`"
            :poster="album.poster" :title="album.title" :subTitle="album.author" :year="album.year" :genre="album.genre"
        />
    </div>
    <Loader v-else-if="albums.length < 1" />
</template>

<script>
import Albumcard from '@/components/Albumcard.vue';
import Loader from '@/components/Loader.vue';
export default {
    name: 'Albums',
    components: {
        Albumcard,
        Loader,
    },
    props: {
        albums: Array,
    },
    data() {
        return {
            storedAlbums: null,
        };
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