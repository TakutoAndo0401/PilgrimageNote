<template>
  <v-app class="header">
    <v-app-bar app clipped-left color="red" dense>
      <v-toolbar-title>
        <v-flex xs12><span id="title">聖地巡礼ノート</span></v-flex>
      </v-toolbar-title>
      <v-spacer />
<!--      <v-icon id="icon" style="font-size: 20px">fas fa-search</v-icon>-->
<!--      <v-flex xs4 md4>-->
<!--      <v-row>-->
<!--        <v-text-field-->
<!--                color="white"-->
<!--                hide-details-->
<!--                placeholder="Search..."-->
<!--                single-line-->
<!--        />-->
<!--      </v-row>-->
<!--      </v-flex>-->
    </v-app-bar>
  </v-app>
</template>

<script>
  export default {
    name: "Header",

    created () {
      this.$vuetify.theme.dark = true
    },
  }
</script>

<style scoped>
  .header {
    height: 60px;
  }
  #title {
    font-size: 20px;
  }
  #icon {
    margin-right: 20px;
  }
</style>
