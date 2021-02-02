<template>
    <v-container>
      <v-row>
        <NewsItem
          v-for="(item, i) in news"
          v-bind:key="i"
          v-bind:image="item.urlToImage"
          v-bind:link="item.url"
          v-bind:title="item.title"
          v-bind:author="item.author"
        >
          {{ item.description }}
        </NewsItem>
      </v-row>
    </v-container>
</template>

<script>
// @ is an alias to /src
import NewsItem from '../components/NewsItem.vue';


export default {
  name: "Rus",
  components: {
    NewsItem,
  },

  data(){
    return {
      news: [],
    }
  },

  methods: {
    getNews() {
      this.axios({
        method: "GET",
        url:
          "https://newsapi.org/v2/top-headlines?country=ru&apiKey=d7f41a32c26b4bbfb596d58b1a54c766",
      }).then((response) => {
        this.news = response.data.articles;
      });
    },
  },

  mounted() {
    this.getNews();
  },
};
</script>
