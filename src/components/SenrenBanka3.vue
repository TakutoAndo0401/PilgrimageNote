<template>
  <v-dialog v-model="dialog8" width="450">
    <v-card>
      <img src="https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/IMG_8678.jpg" class="image" alt="花見小路通"/>
      <v-card-title>
        花見小路通
      </v-card-title>
      <v-card-text>
        <p>ゲーム、千恋*万花の聖地。ここもゲーム開始序盤(CHAPTER 1-1)から登場する。</p>
        <p>場所は<u>京都府京都市祇園町南側</u></p>
        <p>ゲーム開始序盤(CHAPTER 1-1)から登場し、馬庭芦花と一緒に歩く。ここで初めて選択肢が出てくる。</p>
        <p>この場所も海外の方に人気の場所であり、目の前が四条通りのためかなりの観光客で混雑する。狭い道であるにもかかわらず車やバスも通るため落ち着いて見ることはできない。</p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1567.4955481107222!2d135.77462676982023!3d35.0036755961398!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x600108c173e6958f%3A0x792091361351619b!2z6Iqx6KaL5bCP6Lev!5e0!3m2!1sja!2sjp!4v1573114422238!5m2!1sja!2sjp" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
        </div>
      </v-card-text>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn color="primary" @click="close()">
          Close
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
  export default {
    name: "SenrenBanka3",
    data() {
      return {
        dialog8: false
      };
    },
    methods: {
      open() {
        this.dialog8 = true;
      },
      close() {
        this.dialog8 = false;
      }
    }
  }
</script>

<style scoped>
  .image {
    max-width: 70%;
    height: auto;
    display: block;
    margin:0 auto;
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
