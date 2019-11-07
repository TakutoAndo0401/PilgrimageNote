<template>
  <v-app class="header">
    <v-app-bar app clipped-left color="red" dense>
      <v-toolbar-title class="mr-12 align-center">
        <span class="title">聖地巡礼ノート</span>
      </v-toolbar-title>
      <v-spacer />
      <v-row>
        <v-text-field
                placeholder="Search..."
                single-line
                color="white"
                hide-details
        />
      </v-row>
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
</style>
