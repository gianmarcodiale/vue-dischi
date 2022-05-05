<template>
  <header>
      <img src="@/assets/img/Spotify_logo.png" alt="" class="img-fluid">
  </header>
</template>

<script>
export default {
    name: 'SiteHeader'
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/_variables.scss';
header {
    background-color: $footerCardsColor;
    padding: 1rem;
    img {
        width: 50px;
    }
}
</style>