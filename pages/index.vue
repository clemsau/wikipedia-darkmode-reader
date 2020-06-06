<template>
  <div class="text-center mx-auto" style="">
    <span>I want to learn about:</span><SearchArticle v-on:search-text="searchText"/>
    <Article v-if="Object.keys(article).length != 0" :key="1" :title="article.title" :extract="article.extract"/>
    <p v-if="noArticle == 'true'" class="m10">No article is titled {{ searchQuery }}</p>
    <p class="absolute bottom-0 inset-x-0">A side project made by <a href="https://clementsauvage.com">Clément</a></p>
  </div>
</template>

<script>
import axios from 'axios';
import SearchArticle from '~/components/SearchArticle'
import Article from '~/components/Article'

export default {
  components: {
    SearchArticle,
    Article
  },
  data() {
    return {
      article: {},
      noArticle: "",
      searchQuery: ""
    }
  },
  methods: { 
    async searchText(text) {
      this.searchQuery = text
      const config = {
        headers: {Accept: 'application/json'}
      };

      try {
        console.log(`${this.$axios.defaults.baseURL}summary/${text}`);
        const res = axios.get(`${this.$axios.defaults.baseURL}summary/${text}`, config).then((response) => {
            this.title = response.data.title;
            this.noArticle = "";
            this.article = response.data;
        }).catch((error) => {
          this.noArticle = "true";
            this.article = {};
        });
      } catch (err) {
        console.log(err);
      }
    }
  }
}
</script>
