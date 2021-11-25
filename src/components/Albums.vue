<template>
    <div class="albums_container">
        <Albumcard />
    </div>
</template>

<script>
import Albumcard from '@/components/Albumcard.vue';
export default {
    name: 'Albums',
    components: {
        Albumcard,
    },
}
</script>

<style scoped lang="scss">

.albums_container {
    display: flex;
    padding: 120px 80px;
}

</style>