<template>
    <div class="color-palette">
        <div class="background-image-of-box">
            <div class="box-style" :style="currentStyle">
            </div>
        </div>
        <div class="hsl-sliders">
            <Slider caption="Hue:" max="360" valueName="hue" :value="hue" v-on:update-value-event="updateValue"/>
            <Slider caption="Saturation:" max="100" valueName="saturation" :value="saturation" v-on:update-value-event="updateValue"/>
            <Slider caption="Lightness:" max="100" valueName="lightness" :value="lightness" v-on:update-value-event="updateValue"/>
            <Slider caption="Alpha:" max="100" valueName="alpha" :value="alpha" v-on:update-value-event="updateValue"/>
        </div>
    </div>
</template>

<script>
import Slider from './Slider.vue'

export default {
    name: "color-picker",
    components: {
        Slider
    },
    data: function () {
        return {
            hue: 180,
            saturation: 50,
            lightness: 50,
            alpha: 100
        }
    },
    computed: {
        currentStyle: function () {
            return `backgroundColor: hsla(${this.hue}, ${this.saturation}%, ${this.lightness}%, ${this.newAlpha});`
        },
        newAlpha: function () {
            return this.alpha / 100
        }
    },
    methods: {
        updateValue: function (params) {
            this[params.valueName] = params.value
        }
    }
}
</script>

<style scoped>
.color-palette {
  display: flex;
  justify-content: center;
  align-content: center;
  padding: 1em;
}

.background-image-of-box {
  display: flex;
  align-items: center;
} 

.box-style {
  height: 3em;
  width: 3em;
  border: 1px solid #696969;
  border-radius: 1em;
  margin: 1em;
}

.hsl-sliders {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.caption-style {
    font-size: .5em;
}
</style>
