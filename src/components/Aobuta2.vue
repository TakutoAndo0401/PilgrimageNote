<template>
  <v-dialog v-model="dialog10" width="580px">
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
        神奈川県立七里ガ浜高等学校
      </v-card-title>
      <v-card-text>
        <p>アニメ、青春ブタ野郎はバニーガール先輩の夢を見ないの聖地。</p>
        <p>場所は<u>神奈川県鎌倉市七里ガ浜東２丁目３−１</u></p>
        <p>主人公の梓川 咲太やヒロインの桜島 麻衣などが通う高校。作中では峰ヶ原高校として名前が変わっている。</p>
        <p></p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d1233.0728481582619!2d139.51218484338744!3d35.306504489536664!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x60184f43dc650e53%3A0x5dd2121cc9d9437!2z56We5aWI5bed55yM56uL5LiD6YeM44Ks5rWc6auY562J5a2m5qCh!5e0!3m2!1sja!2sjp!4v1579873737914!5m2!1sja!2sjp" width="600" height="450" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
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
    name: "Aobuta2",
    data() {
      return {
        dialog10: false,
        items: [
          {
            src: 'https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/IMG_4092.jpg',
          },
          {
            src: 'https://cdn-ak.f.st-hatena.com/images/fotolife/a/astral01/20190328/20190328002935.jpg',
          }
        ]
      };
    },
    methods: {
      open() {
        this.dialog10 = true;
      },
      close() {
        this.dialog10 = false;
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
