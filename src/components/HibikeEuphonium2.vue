<template>
  <v-dialog v-model="dialog5" width="450">
    <v-card>
      <img src="https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/IMG_6099.jpg" class="image"/>
      <v-card-title>
        大吉山展望台
      </v-card-title>
      <v-card-text>
        <p>アニメ、響け! ユーフォニアムの聖地</p>
        <p>場所は<u>京都府宇治市宇治東内６５−５</u></p>
        <p>1期8話の後半あたりから使われている場所。さわらびの道を宇治上神社から少し北へ行くと登り口がある。</p>
        <p>真夏に1度登ったが、気温が38℃の時で死にかけた。春に登ることをオススメする。虫も多いので注意</p>
        <p>しかし、展望台からは平等院や宇治川を一望でき、夜には宇治市内の夜景が見ることができるとても良いスポットである。</p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3272.5392495730043!2d135.81067651518197!3d34.89291458040727!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x60011173ec277c7d%3A0x2d0f2502468356b0!2z5aSn5ZCJ5bGx5bGV5pyb5Y-w!5e0!3m2!1sja!2sjp!4v1572917736972!5m2!1sja!2sjp" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
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
    name: "HibikeEuphonium2",
    data() {
      return {
        dialog5: false
      };
    },
    methods: {
      open() {
        this.dialog5 = true;
      },
      close() {
        this.dialog5 = false;
      }
    }
  }
</script>

<style scoped>
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
