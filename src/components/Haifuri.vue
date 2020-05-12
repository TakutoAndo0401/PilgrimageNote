<template>
  <v-dialog v-model="dialog12" width="580px">
    <v-card>
      <v-icon id="icon" @click="close()">fas fa-times</v-icon>
      <v-carousel
              cycle
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
        佐野天然温泉 湯処 「のぼり雲」
      </v-card-title>
      <v-card-text>
        <p>アニメ、ハイスクール・フリートの聖地。</p>
        <p>場所は<u>神奈川県横須賀市佐野町４丁目５</u></p>
        <p>OVAの前編で、水雷長 西崎 芽依と砲術長 立石 志摩がこの温泉の休憩所で将棋を指すシーンがある。</p>
        <p>駅からは少し離れた場所にあり、大人は平日1000円と少し高めだが、落ち着いて入れるとても良い温泉である。食事処では、横須賀海軍カレーや潜水艦「なるしお」カレーがあり、とても美味しい。</p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3257.671944536128!2d139.6656313156044!3d35.26441636032481!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x60183f94653f5eeb%3A0xf89cecc6c1df5ef1!2z5L2Q6YeO5aSp54S25rip5rOJIOa5r-WHpuOAjOOBruOBvOOCiumbsuOAjQ!5e0!3m2!1sja!2sjp!4v1579880902451!5m2!1sja!2sjp" width="600" height="450" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
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
    name: "Haifuri",
    data() {
      return {
        dialog12: false,
        items: [
          {
            src: 'https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/IMG_2317.jpg',
          },
        ]
      };
    },
    methods: {
      open() {
        this.dialog12 = true;
      },
      close() {
        this.dialog12 = false;
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
