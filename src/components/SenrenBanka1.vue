<template>
  <v-dialog v-model="dialog6" width="580px">
    <v-card>
      <v-icon id="icon" @click="close()">fas fa-times</v-icon>
      <v-carousel
              height="400"
              hide-delimiter-background
              show-arrows-on-hover
      >
        <v-carousel-item
                v-for="({src},i) in items"
                :key="i"
                :src="src"
        >
        </v-carousel-item>
      </v-carousel>
      <v-card-title>
        祇園白川
      </v-card-title>
      <v-card-text>
        <p>ゲーム、千恋*万花の聖地。ゲーム開始の序盤から登場する場所。</p>
        <p>場所は<u>京都府京都市東山区元吉町７６</u></p>
        <p>ゲーム開始序盤(CHAPTER 1-1)に馬庭芦花と出会う場所。かなりの回数でてくる</p>
        <p>この場所は実際に舞妓さんの姿もみれる場所でもあり、かなり海外の方にも人気のスポットである。春はとても桜が綺麗な場所でもあるので是非とも行って見て欲しい。</p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d204.25330947316826!2d135.7730537114571!3d35.00537958643895!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x600108ea8cfc489b%3A0xdd8e40953bb6e972!2z44CSNjA1LTAwODcg5Lqs6YO95bqc5Lqs6YO95biC5p2x5bGx5Yy65YWD5ZCJ55S677yX77yW!5e0!3m2!1sja!2sjp!4v1572929210579!5m2!1sja!2sjp" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
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
    name: "SenrenBanka1",
    data() {
      return {
        dialog6: false,
        items: [
          {
            src: 'https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/IMG_4816.jpg',
          },
        ]
      };
    },
    methods: {
      open() {
        this.dialog6 = true;
      },
      close() {
        this.dialog6 = false;
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
</style>
