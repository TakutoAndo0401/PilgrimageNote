<template>
  <v-dialog v-model="dialog14" width="580px">
    <v-card>
      <v-icon id="icon" @click="close()">fas fa-times</v-icon>
      <v-carousel
              :height="imageHeight"
              hide-delimiter-background
              hide-delimiters
      >
        <v-carousel-item
                v-for="({src},i) in items"
                :key="i"
                :src="src"
        >
        </v-carousel-item>
      </v-carousel>
      <v-card-title>
        Parc du Champ de Mars(Colmar)
      </v-card-title>
      <v-card-text>
        <p>アニメ、ご注文はうさぎですか?の聖地</p>
        <p>場所は<u>Avenue de la République, 68000 Colmar</u></p>
        <p>この公園は度々登場する公園であり、わかりやすい登場シーンだとシャロがクレープの屋台で働いている所やココアと青山ブルーマウンテンが出会う場面があげられる。</p>
        <p>ここは駅からも近く、コルマール市民の憩いの場となっている広い公園であり、メリーゴーランドが置いてあるのがとても特徴的である。その近くに売店があるのでコーヒーを飲みながらゆったりするのも一興である。</p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2665.8278253536864!2d7.348588115646832!3d48.07496617921853!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x479165dd7154f341%3A0xd8c57274fbc0e852!2z44K344Oj44Oz44O744OJ44O744Oe44Or44K55YWs5ZyS!5e0!3m2!1sja!2sjp!4v1580024575129!5m2!1sja!2sjp" width="600" height="450" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
        </div>
        <v-card-actions>
          <v-spacer></v-spacer>
        </v-card-actions>
        <v-btn class="close-button" v-if="this.$vuetify.breakpoint.xs" @click="close()">Close</v-btn>
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
  export default {
    name: "Gochiusa1",
    data() {
      return {
        dialog14: false,
        items: [
          {
            src: 'https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/IMG_1038.jpeg',
          },
        ]
      };
    },
    computed: {
      imageHeight () {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs': return '240px'
          case 'sm': return '400px'
          case 'md': return '400px'
          case 'lg': return '400px'
          case 'xl': return '400px'
        }
        return this.imageHeight();
      },
    },
    methods: {
      open() {
        this.dialog14 = true;
      },
      close() {
        this.dialog14 = false;
      }
    }
  }
</script>

<style scoped>
  #icon {
    position: absolute;
    margin: 15px 20px;
    font-size: 25px;
    color: black;
    z-index: 1;
  }

  .map {
    position: relative;
    overflow: hidden;
    padding-bottom: 56.25%;
  }
  .map iframe {
    position: absolute;
    left: 0;
    top: 0;
    height: 100%;
    width: 100%;
  }

  .close-button {
    float: right;
    margin-top: -22px;
  }

  @media screen and (max-width: 375px) {
    .map {
      margin: 25px 0 30px
    }
  }
</style>
