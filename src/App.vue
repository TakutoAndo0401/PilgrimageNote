<template>
  <div>
    <div ref="loading" id="loading">
      <img src="https://www.wp-master.club/wp-content/uploads/2018/10/loading.gif" alt="loading">
    </div>
    <div ref="app" class="hidden">
      <Header/>
      <ArticleCard/>
    </div>
  </div>
</template>

<script>
  import ArticleCard from "./components/ArticleCard";
  import Header from "./components/Header";
  export default {
    name: 'App',
    components: {
      Header,
      ArticleCard,
    },
    mounted() {
      let loading =  this.$refs.loading;
      let app = this.$refs.app;
      window.addEventListener('load', function () {
        loading.style.display = 'none';
        app.classList.remove('hidden');
      });
    }
  };
</script>

<style>
  #loading {
    width: 100%;
    height: 100vh;
    background-color: #fff;
    position: relative;
  }
  #loading img {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  .hidden {
    display: none;
  }
</style>
