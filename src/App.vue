<template>
  <div id="app">
    <h1 class="color-picker-header">Color Picker!</h1>
    <ColorPicker />
  </div>
</template>

<script>
import ColorPicker from './components/ColorPicker.vue'

export default {
  name: 'app',
  components: {
    ColorPicker
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.color-picker-header { 
padding-top: .5em;
margin: 0;
font-size: 3em;
}
</style>
