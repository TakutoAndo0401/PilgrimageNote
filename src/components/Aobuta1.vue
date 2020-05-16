<template>
  <v-dialog v-model="dialog9" width="580px">
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
        七里ヶ浜駅
      </v-card-title>
      <v-card-text>
        <p>アニメ、青春ブタ野郎はバニーガール先輩の夢を見ないの聖地。</p>
        <p>場所は<u>江ノ電『七里ケ浜』駅</u></p>
        <p>作中では、1話と5話で駅ホーム内が映し出される。</p>
        <p>江ノ電は土・日・祝日はかなり混むので平日の通勤、通学を避けた時間帯の方がゆっくり雰囲気を味わえる。</p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d13023.958334700366!2d139.5101511!3d35.3062403!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0xb049a943a1009c4b!2z5LiD6YeM44O25rWc6aeF!5e0!3m2!1sja!2sjp!4v1579873374316!5m2!1sja!2sjp" width="600" height="450" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
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
    name: "Aobuta1",
    data() {
      return {
        dialog9: false,
        items: [
          {
            src: 'https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/IMG_8676.jpg',
          },
        ],
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
        this.dialog9 = true;
      },
      close() {
        this.dialog9 = false;
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
