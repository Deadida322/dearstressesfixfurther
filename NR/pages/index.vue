<template>
  <v-row justify="center" align="center">
    <v-container class="d-flex justify-center align-center">
      <v-btn
        nuxt
        id="vue-btn"
        to="/news"
      >news</v-btn>
      <br>
      <br>
      <v-btn
        nuxt
        id="vue-btn2"
        to="/north"
      >north</v-btn>
    </v-container>
  </v-row>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>
