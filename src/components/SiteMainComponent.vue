<template>
  <section>
    <div class="container">
      <div class="row row-cols-5">
        <div class="col" v-for="(album, index) in albumsList" :key="index">
          <div class="album-card">
            <img :src="album.poster" alt="" class="img-fluid">
            <div class="title text-white text-uppercase text-center">{{album.title}}</div>
            <div class="author-info text-center">
              <div>{{album.author}}</div>
              <div>{{album.year}}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios'
export default {
    name: 'SiteMain',
    data() {
      return {
        link: 'https://flynn.boolean.careers/exercises/api/array/music',
        albumsList: null,
        loading: true
      }
    },
    methods: {
      callApi() {
        axios
        .get(this.link)
        .then((response) => {
          //console.log(response);
          this.albumsList = response.data.response;
          this.loading = false;
        })
        .catch((error) => {
          console.log(error);
        })
      }
    },
    mounted() {
      this.callApi()
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/_variables.scss';
section {
  padding: 2rem 0;
  .album-card {
    padding: 1rem;
    background-color: $footerCardsColor;
    height: calc(100vh / 1.2);
    margin: 0.5rem;
    .title {
      font-size: 0.9rem;
      padding: 1rem 0;
    }
    .author-info {
      color: $artistTextColor;
      flex-grow: 1;
    }
  }
}
</style>