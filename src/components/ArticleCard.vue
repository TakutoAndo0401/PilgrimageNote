<template>
  <v-app>
    <v-row justify="center" style="margin: 0" >
      <v-col v-for="(article, id) in articles" :key="id">
        <v-card class="card" elevation=20 slot="activator" @click="show(article.index)">
          <v-img class="white--text align-end" height="200px" :src="article.image" alt="">
            <v-card-title class="title">{{ article.title }}</v-card-title>
          </v-img>
          <v-card-subtitle class="pb-0">{{ article.date }}</v-card-subtitle>
          <v-card-text class="text--primary">
            <div class="name">{{ article.name }}</div>
            <div>{{ article.place1 }}</div>
            <div>{{ article.place2 }}</div>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>

    <Saekano1 ref="dialog1"></Saekano1>
    <Saekano2 ref="dialog2"></Saekano2>
    <Saekano3 ref="dialog3"></Saekano3>
    <HibikeEuphonium1 ref="dialog4"></HibikeEuphonium1>
    <HibikeEuphonium2 ref="dialog5"></HibikeEuphonium2>
    <SenrenBanka1 ref="dialog6"></SenrenBanka1>
    <SenrenBanka2 ref="dialog7"></SenrenBanka2>
    <SenrenBanka3 ref="dialog8"></SenrenBanka3>
  </v-app>
</template>

<script>
  import Saekano1 from "./Saekano1";
  import Saekano2 from "./Saekano2";
  import Saekano3 from "./Saekano3";
  import HibikeEuphonium1 from "./HibikeEuphonium1";
  import HibikeEuphonium2 from "./HibikeEuphonium2";
  import SenrenBanka1 from "./SenrenBanka1";
  import SenrenBanka2 from "./SenrenBanka2";
  import SenrenBanka3 from "./SenrenBanka3";
  import axios from 'axios';
  export default {
    name: "ArticleCard",
    components: {
      SenrenBanka3,
      SenrenBanka2,
      SenrenBanka1,
      HibikeEuphonium2,
      HibikeEuphonium1,
      Saekano3,
      Saekano1,
      Saekano2,
    },
    methods: {
      show(index) {
        this.$refs[`dialog${index}`].open();
      }
    },
    data() {
      return {
        articles: [],
      }
    },
    mounted() {
      axios
          .get("https://pilgrimage-note-api.herokuapp.com/api/articles")
          .then(response => (this.articles = response.data))
    },
  }
</script>

<style scoped>
  .card {
    max-width: 400px;
    max-height: 320px;
    margin: 0 auto;
    ovarflow-y: hidden;
  }
  
  .title {
    margin-bottom: -15px;
  }
  
  .name {
    margin-bottom: 5px;
  }
</style>
