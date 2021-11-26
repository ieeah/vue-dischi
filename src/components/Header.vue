<template>
    <header>
        <img class="brand_logo" src="@/assets/logo.png" alt="">

        <form action="">
            <select v-model="selectedGenre" @change="$emit('genResearch', selectedGenre)">
                <option value="none"></option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
            </select>
            <button @click.prevent="$emit('genResearch', selectedGenre)">Cerca</button>
        </form>
    </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            selectedGenre: '',
        };
    },
}
</script>

<style scoped lang="scss">
@import '@/styles/globals.scss';
@import '@/styles/vars.scss';
    header {
        background-color: $secondary-color;
        padding: 10px;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    .brand_logo {
        height: 48px;
    }

    select,
    button {
        padding: 5px 10px;
    }

    select {
        width: 80px;
        text-align: center;
    }

    button {
        margin-left: 15px;
    }
</style>