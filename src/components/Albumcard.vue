<template>
    <div class="album_card">
        <div class="card_img">
            <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
        </div>
        <div class="card_details">
            <h3>NEW JERSEY</h3>
            <h4>Bon Jovi</h4>
            <h5>1988</h5>
            <h5 class="genre">Rock</h5>
        </div>
    </div>
</template>

<script>

export default {
    name: 'Albumcard',
}
</script>

<style scoped lang="scss">
@import '@/styles/vars.scss';
.album_card {
    text-align: center;
    background-color: $secondary-color;
    margin-bottom: 20px;
    padding: 20px;
    width: calc(100% / 8);
    height: 100%;
    .card_img {
        margin-bottom: 20px;
        img {
        width: 100%;
    }
    }
    .card_details {
        h3 {
            color: $clear-text;
            padding-bottom: 20px;
            font-size: 1.3rem;
        }
        h4,
        h5 {
            color: $third-color;
            padding-bottom: 8px;
            font-size: 1.1rem;
        }
        .genre {
            color: $clear-text;
            font-size: 1rem;
        }
    }
}

</style>