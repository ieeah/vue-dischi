<template>
  <header>
      <img class="brand_logo" src="@/assets/logo.png" alt="">
  </header>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style scoped lang="scss">
@import '@/styles/vars.scss';
    header {
        background-color: $secondary-color;
        padding: 7px;
    }

    .brand_logo {
        height: 48px;
    }
</style>