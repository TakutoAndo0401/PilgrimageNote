<template>
  <v-dialog v-model="dialog11" width="580px">
    <v-card>
      <v-icon id="icon" @click="close()">fas fa-times</v-icon>
      <img src="https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/IMG_2284.jpg" class="image" alt=""/>
      <v-card-title>
        江の島大橋・江の島弁天橋
      </v-card-title>
      <v-card-text>
        <p>アニメ、青春ブタ野郎はバニーガール先輩の夢を見ないの聖地。</p>
        <p>場所は<u>神奈川県藤沢市江の島</u></p>
        <p>アニメ5話で古賀 朋絵と新江ノ島水族館のデート後に登場する。(8分45秒)</p>
        <p>この辺りは景色がかなり綺麗で特に夕方あたりがオススメ。車で行くとかなりの渋滞で辛い思いをするので電車で行くのがよい。</p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3256.054822133098!2d139.4802341156052!3d35.30461925814085!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x60184ee35936e1ad%3A0x9bc2dd80d5870730!2z5rGf44Gu5bO25aSn5qmL44O75rGf44Gu5bO25byB5aSp5qmL!5e0!3m2!1sja!2sjp!4v1579875226488!5m2!1sja!2sjp" width="600" height="450" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
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
    name: "Aobuta3",
    data() {
      return {
        dialog11: false
      };
    },
    methods: {
      open() {
        this.dialog11 = true;
      },
      close() {
        this.dialog11 = false;
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
