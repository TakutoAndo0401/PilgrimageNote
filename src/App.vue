<template>
  <div>
    <vue-element-loading :active="isActive" spinner="bar-fade-scale" :is-full-screen="true"/>
    <Header/>
    <ArticleCard/>
  </div>
</template>

<script>
  import ArticleCard from "./components/ArticleCard";
  import Header from "./components/Header";
  import VueElementLoading from 'vue-element-loading'
  export default {
    name: 'App',

    components: {
      Header,
      ArticleCard,
      VueElementLoading
    },
  };
</script>
