<template lang="pug">
  .app
    Main
</template>

<script>
import Main from './components/Main.vue'

export default {
  name: 'app',
  components: {
    Main
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Roboto');

body {
  margin: 0;
  font-family: 'Roboto', sans-serif;
}
</style>
