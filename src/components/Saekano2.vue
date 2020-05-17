<template>
  <v-dialog v-model="dialog2" width="580px">
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
        都電荒川線学習院下駅すぐの踏切
      </v-card-title>
      <v-card-text>
        <p>アニメ、冴えない彼女の育てかたの聖地</p>
        <p>場所は<u>東京都豊島区高田２丁目７</u></p>
        <p>駅を降りてすぐの踏切で早稲田方面を望遠でとると上手く撮れる。自分が撮った写真は逆方向...</p>
        <p>1期のオープニングで自転車を押して歩く安芸倫也とその他５人のヒロインが渡るところである。</p>
        <p></p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2900.8109281150155!2d139.71173694093466!3d35.716359143737506!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x60188d159360df57%3A0xce7ad37d9d11566!2z5a2m57-S6Zmi5LiL6aeF!5e0!3m2!1sja!2sjp!4v1572868401399!5m2!1sja!2sjp"  frameborder="0" style="border:0;" allowfullscreen=""></iframe>
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
    name: "Saekano2",
    data() {
      return {
        dialog2: false,
        items: [
          {
            src: 'https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/saekano2.jpeg',
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
        this.dialog2 = true;
      },
      close() {
        this.dialog2 = false;
      }
    }
  }
</script>

<style scoped>
  #icon {
    position: absolute;
    margin: 15px 20px;
    font-size: 25px;
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
