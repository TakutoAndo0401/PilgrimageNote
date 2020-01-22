<template>
  <v-app style="background-color: #212121">
    <v-app-bar app clipped-left color="#333333" dense>
      <v-toolbar-title>
        <v-flex xs12><span id="title">聖地巡礼ノート</span></v-flex>
      </v-toolbar-title>
      <v-spacer />
      <v-icon id="icon">fas fa-search</v-icon>
      <v-flex xs4 md4>
        <v-row>
          <v-text-field
                  color="white"
                  hide-details
                  placeholder="Search..."
                  single-line
                  v-model="search_term"
          />
        </v-row>
      </v-flex>
    </v-app-bar>
    <vue-loading v-show="loading" type="spin" color="#fff" :size="{ width: '100px', height: '100px' }"/>
    <section v-if="errored" class="errored">
      <p>We're sorry, we're not able to retrieve this articles at the moment, please try back later</p>
    </section>
    <transition name="slide-fade">
      <v-row style="margin-top: 60px" v-show="!loading" class="row">
        <v-col v-for="(article, id) in articles" :key="id" style="flex-grow: 0">
          <v-hover
                  v-slot:default="{ hover }"
                  :open-delay="openDelay"
                  :close-delay="closeDelay"
                  :disabled="disabled"
                  :value="value"
          >
            <v-card class="card" color="#333333" slot="activator" @click="show(article.index)" :elevation="hover ? 12 : 2">
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
          </v-hover>
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
      },
      getArticles: function() {
        let api_url = "https://pilgrimage-note-api.herokuapp.com/api/articles";
        if (this.search_term !== "" || this.search_term !== null) {
          api_url = `https://pilgrimage-note-api.herokuapp.com/api/articles?word=${this.search_term}`;
        }
        axios
            .get(api_url)
            .then(response => {
              this.articles = response.data;
            })
      }
    },
    data() {
      return {
        articles: [],
        loading: true,
        errored: false,
        search_term: "",
        disabled: false,
        openDelay: '0',
        closeDelay: '0',
        value: false,
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
    created() {
      window.addEventListener("keyup", this.getArticles);
      this.$vuetify.theme.dark = true;
    },
  }
</script>

<style scoped>
  #title {
    font-size: 20px;
  }
  #icon {
    font-size: 20px;
    margin: -30px;
  }
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

  .row {
    justify-content: space-between;
    margin: 0 40px;
  }

  @media screen and ( max-width:1024px) {
    .row {
      justify-content: center;
      margin: 0;
    }
    #icon {
      margin: 10px;
    }
  }
  
  /*.fade-enter-active {*/
  /*  will-change: opacity;*/
  /*  transition: opacity 3000ms cubic-bezier(0.2, 0, 0, 1) 0ms;*/
  /*}*/
  /*.fade-enter {*/
  /*  opacity: 0*/
  /*}*/
  
  
  .slide-fade-enter-active {
    transition:all .700s cubic-bezier(0.2, 0, 0, 1) 0ms;;
  }
  
  .slide-fade-enter {
    transform: translateY(1000px);
    opacity: 0;
  }
</style>
