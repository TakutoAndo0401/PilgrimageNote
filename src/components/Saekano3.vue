<template>
  <v-dialog v-model="dialog3" width="580px">
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
        都電荒川線面影橋駅を降りた正面
      </v-card-title>
      <v-card-text>
        <p>アニメ、冴えない彼女の育てかたの聖地</p>
        <p>場所は<u>東京都豊島区高田２丁目１−１６</u></p>
        <p>アニメ1期4話の約3分21秒から登場するシーン。</p>
        <p>この場所は春になると桜でとても綺麗らしい。</p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d883.6948952123602!2d139.71382120688912!3d35.71304903088923!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x60188d17058f01dd%3A0xc9a3fe6359febada!2z6Z2i5b2x5qmL6aeF!5e0!3m2!1sja!2sjp!4v1572875248607!5m2!1sja!2sjp" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
        </div>
      </v-card-text>
      <v-card-actions>
        <v-spacer></v-spacer>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
  export default {
    name: "Saekano3",
    data() {
      return {
        dialog3: false,
        items: [
          {
            src: 'https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/IMG_2536.jpg',
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
        this.dialog3 = true;
      },
      close() {
        this.dialog3 = false;
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
</style>
