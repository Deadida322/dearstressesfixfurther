<template>
  <v-app v-if="show">
    <v-main>
      <v-container class="w-100">
        <Nuxt class="w-100 z-index-1"/>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      show: true
    }
  }
}
</script>
