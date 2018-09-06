<template>
    <div class="color-palette">
        <div class="background-image-of-box">
            <div class="box-style" :style="currentStyle">
            </div>
        </div>
        <div class="hsl-sliders">
            <section class="slider-hue">
                <section class="caption-style">Hue:</section>
                <input type="range" min="0" max="360" v-model="hue" />
            </section>
            <section class="slider-saturation">
                <section class="caption-style">Saturation:</section>
                <input type="range" min="0" max="100" v-model="saturation" />
            </section>
            <section class="slider-lightness">
                <section class="caption-style">Lightness:</section>
                <input type="range" min="0" max="100" v-model="lightness" />
            </section>
            <section class="slider-alpha">
                <section class="caption-style">Alpha:</section>
                <input type="range" min="0" max="100" v-model="alpha" />
            </section>
        </div>
    </div>
</template>

<script>
export default {
    name: "color-picker",
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
    }
}
</script>

<style>
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
