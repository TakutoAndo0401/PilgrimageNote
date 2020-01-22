<template>
  <v-dialog v-model="dialog1" width="580px">
    <v-card>
      <v-icon id="icon" @click="close()">fas fa-times</v-icon>
      <img src="https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/EIVi2hOXYAEyylZ.jpeg" class="image" alt=""/>
      <v-card-title>
        のぞき坂(別名:胸突坂)
      </v-card-title>
      <v-card-text>
        <p>アニメ、冴えない彼女の育てかたの聖地</p>
        <p>場所は<u>東京都豊島区高田２丁目１２−２１</u></p>
        <p>東京都内で自動車通行が可能な道路としては、傾斜・延長距離ともに最急の一つに数えられる坂で、別名は胸突坂と呼ばれている。</p>
        <p>オープニングや加藤恵と出会う第1話から沢山出ており、安芸倫也の家の近所と設定されている。</p>
        <div class="map">
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1619.683901018766!2d139.7126524983254!3d35.71717196688231!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x60188d15b20ad283%3A0xe876c38539a950e2!2z44Gu44Ge44GN5Z2C!5e0!3m2!1sja!2sjp!4v1572853611817!5m2!1sja!2sjp" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
        </div>
        <v-card-actions>
          <v-spacer></v-spacer>
        </v-card-actions>
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
  export default {
    name: "Dialog",
    data() {
      return {
        dialog1: false
      };
    },
    methods: {
      open() {
        this.dialog1 = true;
      },
      close() {
        this.dialog1 = false;
      }
    }
  }
</script>

<style scoped>
  #icon {
    position: absolute;
    margin: 15px 20px;
    font-size: 25px;
  }
  
  .image {
    max-width: 100%;
    height: auto;
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
