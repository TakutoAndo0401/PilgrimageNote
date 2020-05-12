<template>
  <v-dialog v-model="dialog15" width="580px">
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
        Restaurant Au Chasseur
      </v-card-title>
      <v-card-text>
        <p>アニメ、ご注文はうさぎですか?の聖地</p>
        <p>場所は<u>4 Rue du Chasseur, 68000 Colmar</u></p>
        <p>ここはラビットハウスのモチーフになっているレストラン。店内は作中と違く、喫茶店ではないがコーヒーは飲める。</p>
        <p>中心部に近い場所にあるがお店の営業日や営業時間は決まってないため、数日宿泊する必要がある。メニューはどれもボリューム満点でアルザス地方特有の料理が食べられる。</p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1083.86804639084!2d7.360726849479362!3d48.07715054896281!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0xb45abbbfde931008!2sRestaurant%20Au%20Chasseur!5e0!3m2!1sja!2sjp!4v1580026154245!5m2!1sja!2sjp" width="600" height="450" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
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
    name: "Gochiusa2",
    data() {
      return {
        dialog15: false,
        items: [
          {
            src: 'https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/IMG_0977.jpeg',
          },
        ]
      };
    },
    methods: {
      open() {
        this.dialog15 = true;
      },
      close() {
        this.dialog15 = false;
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
