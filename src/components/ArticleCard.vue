<template>
  <v-app>
    <vue-loading v-show="loading" type="spin" color="#fff" :size="{ width: '100px', height: '100px' }"/>
    <section v-if="errored" class="errored">
      <p>We're sorry, we're not able to retrieve this articles at the moment, please try back later</p>
    </section>
    <transition name="slide-fade">
      <v-row justify="center" style="margin: 0" v-show="!loading">
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
    </transition>
  
    <Saekano1 ref="dialog1"/>
    <Saekano2 ref="dialog2"/>
    <Saekano3 ref="dialog3"/>
    <HibikeEuphonium1 ref="dialog4"/>
    <HibikeEuphonium2 ref="dialog5"/>
    <SenrenBanka1 ref="dialog6"/>
    <SenrenBanka2 ref="dialog7"/>
    <SenrenBanka3 ref="dialog8"/>
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
  import { VueLoading } from 'vue-loading-template'
  export default {
    name: "ArticleCard",
    components: {
      VueLoading,
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
        loading: true,
        errored: false
      }
    },
    beforeCreate() {
      axios
          .get("https://pilgrimage-note-api.herokuapp.com/api/articles")
          //axiosの処理が成功した場合に処理
          .then(response => {
            this.articles = response.data;
          })
          .catch(() => {
            //axiosの処理にエラーが発生した場合に処理
            this.errored = true
          })
          //axiosの処理結果によらずいつも実行させたい処理
          .finally(() => this.loading = false)
    },
  }
</script>

<style scoped>
  .errored {
    text-align: center;
    margin-top: 20%;
  }
  .card {
    width: 400px;
    height: 320px;
    margin: 0 auto;
    ovarflow-y: hidden;
  }
  
  .title {
    margin-bottom: -15px;
  }
  
  .name {
    margin-bottom: 5px;
  }

  /*
  .fade-enter-active {
    will-change: opacity;
    transition: opacity 3000ms cubic-bezier(0.2, 0, 0, 1) 0ms;
  }
  .fade-enter {
    opacity: 0
  }
  */
  
  .slide-fade-enter-active {
    transition: all .5s ease;
  }
  
  .slide-fade-enter {
    transform: translateY(300px);
    opacity: 0;
  }
</style>
