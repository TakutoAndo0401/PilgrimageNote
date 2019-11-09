<template>
  <v-app>
    <v-row justify="center" style="margin: 0">
      <v-col>
        <v-card class="card" elevation=20 slot="activator" @click="show1()">
          <v-img class="white--text align-end" height="200px" src="../../public/img/EIVi2hOXYAEyylZ.jpeg">
            <v-card-title class="title">のぞき坂</v-card-title>
          </v-img>
          
          <v-card-subtitle class="pb-0">2019年11月1日</v-card-subtitle>
          
          <v-card-text class="text--primary">
            <div class="name">アニメ:冴えない彼女の育てかたOPなど</div>
            <div>都電荒川線学習院下駅、東京メトロ副都心線雑司が谷駅3番出口から徒歩2分程度</div>
          </v-card-text>
          <Saekano1 ref="dialog1"></Saekano1>
        </v-card>
      </v-col>
    
      <v-col>
        <v-card class="card" elevation=20 slot="activator" @click="show2()">
          <v-img class="white--text align-end" height="200px" src="../../public/img/saekano2.jpeg">
            <v-card-title class="title">都電荒川線学習院下駅踏切</v-card-title>
          </v-img>
        
          <v-card-subtitle class="pb-0">2019年11月1日</v-card-subtitle>
        
          <v-card-text class="text--primary">
            <div class="name">アニメ:冴えない彼女の育てかたOP</div>
            <div>都電荒川線学習院下駅を降りてすぐの踏切</div>
          </v-card-text>
          <Saekano2 ref="dialog2"></Saekano2>
        </v-card>
      </v-col>
  
      <v-col>
        <v-card class="card" elevation=20 slot="activator" @click="show3()">
          <v-img class="white--text align-end" height="200px" src="../../public/img/IMG_2536.jpg">
            <v-card-title class="title">都電荒川線面影橋駅</v-card-title>
          </v-img>
      
          <v-card-subtitle class="pb-0">2019年11月1日</v-card-subtitle>
      
          <v-card-text class="text--primary">
            <div class="name">アニメ:冴えない彼女の育てかた4話</div>
            <div>都電荒川線面影橋駅を降りた正面</div>
          </v-card-text>
          <Saekano3 ref="dialog3"></Saekano3>
        </v-card>
      </v-col>
  
      <v-col>
        <v-card class="card" elevation=20 slot="activator" @click="show4()">
          <v-img class="white--text align-end" height="200px" src="../../public/img/IMG_2430.jpg">
            <v-card-title class="title">京都駅</v-card-title>
          </v-img>
      
          <v-card-subtitle class="pb-0">2019年5月3日</v-card-subtitle>
      
          <v-card-text class="text--primary">
            <div class="name">アニメ:響け! ユーフォニアム、やはり俺の青春ラブコメはまちがっている。など多数</div>
            <div>京都駅中央口JRホーム側改札外</div>
          </v-card-text>
          <HibikeEuphonium1 ref="dialog4"></HibikeEuphonium1>
        </v-card>
      </v-col>
  
      <v-col>
        <v-card class="card" elevation=20 slot="activator" @click="show5()">
          <v-img class="white--text align-end" height="200px" src="../../public/img/IMG_6099.jpg">
            <v-card-title class="title">大吉山</v-card-title>
          </v-img>
      
          <v-card-subtitle class="pb-0">2018年7月26日</v-card-subtitle>
      
          <v-card-text class="text--primary">
            <div class="name">アニメ:響け! ユーフォニアム1期8話</div>
            <div>京阪宇治線宇治駅から徒歩20分</div>
            <div>JR奈良線宇治駅から徒歩30分</div>
          </v-card-text>
          <HibikeEuphonium2 ref="dialog5"></HibikeEuphonium2>
        </v-card>
      </v-col>
  
      <v-col>
        <v-card class="card" elevation=20 slot="activator" @click="show6()">
          <v-img class="white--text align-end" height="200px" src="../../public/img/IMG_4816.jpg">
            <v-card-title class="title">祇園白川</v-card-title>
          </v-img>
      
          <v-card-subtitle class="pb-0">2019年4月2日</v-card-subtitle>
      
          <v-card-text class="text--primary">
            <div class="name">ゲーム:千恋*万花 序盤共通ルートなど多数</div>
            <div>京阪電車祇園四条駅から徒歩5分</div>
          </v-card-text>
          <SenrenBanka1 ref="dialog6"></SenrenBanka1>
        </v-card>
      </v-col>
      
      <v-col>
        <v-card class="card" elevation=20 slot="activator" @click="show7()">
          <v-img class="white--text align-end" height="200px" src="../../public/img/IMG_6328.jpg">
            <v-card-title class="title">産寧坂（三年坂）</v-card-title>
          </v-img>
      
          <v-card-subtitle class="pb-0">2018年7月26日</v-card-subtitle>
      
          <v-card-text class="text--primary">
            <div class="name">ゲーム:千恋*万花 常陸茉子と鮎を食べる場所など多数</div>
            <div>京阪電車祇園四条駅から徒歩20分。付近には清水寺がある</div>
          </v-card-text>
          <SenrenBanka2 ref="dialog7"></SenrenBanka2>
        </v-card>
      </v-col>
  
      <v-col>
        <v-card class="card" elevation=20 slot="activator" @click="show8()">
          <v-img class="white--text align-end" height="200px" src="../../public/img/IMG_8678.jpg">
            <v-card-title class="title">花見小路通</v-card-title>
          </v-img>

          <v-card-subtitle class="pb-0">2018年7月26日</v-card-subtitle>

          <v-card-text class="text--primary">
            <div class="name">ゲーム:千恋*万花 序盤共通ルート</div>
            <div>京阪電車祇園四条駅から徒歩3分</div>
          </v-card-text>
          <SenrenBanka3 ref="dialog8"></SenrenBanka3>
        </v-card>
      </v-col>
  
      <v-col>
        <v-card class="card" elevation=20 slot="activator" @click="show9()">
          <v-img class="white--text align-end" height="200px" src="../../public/img/IMG_8676.jpg">
            <v-card-title class="title">七里ヶ浜駅</v-card-title>
          </v-img>
      
          <v-card-subtitle class="pb-0">2019年3月5日</v-card-subtitle>
      
          <v-card-text class="text--primary">
            <div class="name">アニメ:青春ブタ野郎はバニーガール先輩の夢を見ない</div>
            <div>七里ヶ浜駅前</div>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
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
    }
  }
</script>

<style scoped>
  .card {
    max-width: 400px;
    max-height: 320px;
    margin: 0 auto;
  }
  
  .title {
    margin-bottom: -15px;
  }
  
  .name {
    margin-bottom: 5px;
  }
</style>
