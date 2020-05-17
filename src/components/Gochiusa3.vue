<template>
  <v-dialog v-model="dialog16" width="580px">
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
        La Petite Venise
      </v-card-title>
      <v-card-text>
        <p>アニメ、ご注文はうさぎですか?の聖地</p>
        <p>場所は<u>Quai de la Poissonnerie, 68000 Colmar</u></p>
        <p>ご注文はうさぎですか??(2期)のEDでチマメ隊がダンスをする場所。通称「チマメ橋」</p>
        <p>木組みの家と石畳の街に来た実感を味わうことができる素晴らしいスポット。多くの観光客が訪れるので人が映らないように写真を撮るには早朝に来るのが良い。</p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d666.4661092790886!2d7.359679072136502!3d48.07425952308923!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x479165ef5006a63d%3A0xe758095d72e39015!2z44OpIOODl-ODgSDjg7Tjgqfjg4vjgrk!5e0!3m2!1sja!2sjp!4v1580026227482!5m2!1sja!2sjp" width="600" height="450" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
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
    name: "Gochiusa3",
    data() {
      return {
        dialog16: false,
        items: [
          {
            src: 'https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/IMG_1063.JPG',
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
        this.dialog16 = true;
      },
      close() {
        this.dialog16 = false;
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
