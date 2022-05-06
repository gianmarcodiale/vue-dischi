<template>
  <header class="d-flex justify-content-between">
    <img src="@/assets/img/Spotify_logo.png" alt="" class="img-fluid" />
    <select name="selectGenre" id="selectGenre">
      <option selected>Select genre</option>
      <option value="rock">Rock</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
      <option value="pop">Pop</option>
    </select>
  </header>
</template>

<script>
export default {
  name: "SiteHeader",
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/_variables.scss";
header {
  background-color: $footerCardsColor;
  padding: 1rem;
  select {
    padding: 0.5rem;
  }
  img {
    width: 50px;
  }
}
</style>
