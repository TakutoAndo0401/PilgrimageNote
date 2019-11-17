<template>
  <v-app>
    <v-row justify="center" style="margin: 0">
      <v-col v-for="(article, index) in articles" :key="index">
        <v-card class="card" elevation=20 slot="activator" @click="article.show">
          <v-img class="white--text align-end" height="200px" v-bind:src="article.image" alt="">
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
  export default {
    name: "ArticleCard",
    methods: {
      show1() {
        this.$refs.dialog1.open();
      },
      show2() {
        this.$refs.dialog2.open();
      },
      show3() {
        this.$refs.dialog3.open();
      },
      show4() {
        this.$refs.dialog4.open();
      },
      show5() {
        this.$refs.dialog5.open();
      },
      show6() {
        this.$refs.dialog6.open();
      },
      show7() {
        this.$refs.dialog7.open();
      },
      show8() {
        this.$refs.dialog8.open();
      },
      show9() {
        this.$refs.dialog9.open();
      }
    },
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

    data: function() {
      return {
        articles: [
          {
            show: this.show1,
            image: 'img/EIVi2hOXYAEyylZ.jpeg',
            title: 'のぞき坂',
            date: '2019年11月1日',
            name: 'アニメ:冴えない彼女の育てかたOPなど',
            place1: '都電荒川線学習院下駅、東京メトロ副都心線雑司が谷駅3番出口から徒歩2分程度',
          },
          {
            show: this.show2,
            image: 'img/saekano2.jpeg',
            title: '都電荒川線学習院下駅踏切',
            date: '2019年11月1日',
            name: 'アニメ:冴えない彼女の育てかたOP',
            place1: '都電荒川線学習院下駅を降りてすぐの踏切',
          },
          {
            show: this.show3,
            image: 'img/IMG_2536.jpg',
            title: '都電荒川線面影橋駅',
            date: '2019年11月1日',
            name: 'アニメ:冴えない彼女の育てかた4話',
            place1: '都電荒川線面影橋駅を降りた正面',
          },
          {
            show: this.show4,
            image: 'img/IMG_2430.jpg',
            title: '京都駅',
            date: '2019年5月3日',
            name: 'アニメ:響け! ユーフォニアム、やはり俺の青春ラブコメはまちがっている。など多数',
            place1: '京阪宇治線宇治駅から徒歩20分',
          },
          {
            show: this.show5,
            image: 'img/IMG_6099.jpg',
            title: '大吉山',
            date: '2018年7月26日',
            name: 'アニメ:響け! ユーフォニアム1期8話',
            place1: '京都駅中央口JRホーム側改札外',
            place2: 'JR奈良線宇治駅から徒歩30分'
          },
          {
            show: this.show6,
            image: 'img/IMG_4816.jpg',
            title: '祇園白川',
            date: '2019年4月2日',
            name: 'ゲーム:千恋*万花 序盤共通ルートなど多数',
            place1: '京阪電車祇園四条駅から徒歩5分',
          },
          {
            show: this.show7,
            image: 'img/IMG_6328.jpg',
            title: '産寧坂（三年坂）',
            date: '2018年7月26日',
            name: 'ゲーム:千恋*万花 常陸茉子と鮎を食べる場所など多数',
            place1: '京阪電車祇園四条駅から徒歩20分',
          },
          {
            show: this.show8,
            image: 'img/IMG_8678.jpg',
            title: '花見小路通',
            date: '2018年7月26日',
            name: 'ゲーム:千恋*万花 序盤共通ルート',
            place1: '京阪電車祇園四条駅から徒歩3分',
          },
          {
            show: this.show9,
            image: 'img/IMG_8676.jpg',
            title: '七里ヶ浜駅',
            date: '2019年3月5日',
            name: 'アニメ:青春ブタ野郎はバニーガール先輩の夢を見ない',
            place1: '七里ヶ浜駅前',
          },
        ]
      };
    }
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
