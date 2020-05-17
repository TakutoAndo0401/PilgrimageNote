<template>
  <v-dialog v-model="dialog13" width="580px">
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
        樺崎八幡宮
      </v-card-title>
      <v-card-text>
        <p>アニメ、ヨスガノソラの聖地。</p>
        <p>場所は<u>栃木県足利市樺崎町１７２３</u></p>
        <p>作中では「叉依姫神社」として、アニメでは各話で登場しゲームでは別アングルでこの神社が映し出される。</p>
        <p>駅からは離れており行きづらい場所ではあるが、タクシーを利用する場合は15分で着く。車の場合は駐車場もあるので大丈夫。駅近くのはレンタサイクルがあり、1日800円でレンタルできるのでこれを利用するのもアリ。</p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3212.955630482799!2d139.49257781562477!3d36.36185359995004!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x601f228cd4d59a5b%3A0xc344c8ea1d862474!2z5qi65bSO5YWr5bmh5a6u!5e0!3m2!1sja!2sjp!4v1580022882483!5m2!1sja!2sjp" width="600" height="450" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
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
    name: "Yosuganosora",
    data() {
      return {
        dialog13: false,
        items: [
          {
            src: 'https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/IMG_1975.jpg',
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
        this.dialog13 = true;
      },
      close() {
        this.dialog13 = false;
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
