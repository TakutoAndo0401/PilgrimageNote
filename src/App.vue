<template>
  <div>
    <div v-show="loading"><pulse-loader></pulse-loader></div>
    <div v-show="!loading">
      <Header/>
      <ArticleCard/>
    </div>
  </div>
</template>

<script>
  import ArticleCard from "./components/ArticleCard";
  import Header from "./components/Header";
  import PulseLoader from "vue-spinner/src/PulseLoader";

  export default {
    name: 'App',
    components: {
      Header,
      ArticleCard,
      PulseLoader
    },
    data: function() {
      return {
        loading: true
      };
    },
    mounted() {
      setTimeout(() => {
        this.loading = false;
      }, 2000);
    }
  };
</script>
