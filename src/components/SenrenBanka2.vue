<template>
  <v-dialog v-model="dialog7" width="580px">
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
        産寧坂（三年坂）
      </v-card-title>
      <v-card-text>
        <p>ゲーム、千恋*万花の聖地。ゲーム開始の序盤や常陸茉子と鮎を食べる場所で登場する。</p>
        <p>場所は<u>京都府京都市東山区清水２丁目２２１</u></p>
        <p>ゲーム開始序盤(CHAPTER 1-1)から登場し、常陸茉子と鮎を食べる場所でもある。</p>
        <p>この場所は、かなり海外の観光客で賑わっている場所である。お土産やお食事処もあり、京都感たっぷりの場所。近くに清水寺もあるのでチェック</p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d435.35270870892265!2d135.78095135314214!3d34.99638402710075!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x60010879a219f8af%3A0xa3504d2600725c07!2z55Sj5a-n5Z2C77yI5LiJ5bm05Z2C77yJ!5e0!3m2!1sja!2sjp!4v1572968422942!5m2!1sja!2sjp" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
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
    name: "SenrenBanka2",
    data() {
      return {
        dialog7: false,
        items: [
          {
            src: 'https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/IMG_6328.jpg',
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
        this.dialog7 = true;
      },
      close() {
        this.dialog7 = false;
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
