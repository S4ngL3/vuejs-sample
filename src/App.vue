<template>
  <FingerPrint msg="Unique your device ids information"/>
</template>

<script>
import FingerPrint from './components/finger-print.vue'

export default {
  name: 'App',
  components: {
    FingerPrint
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
