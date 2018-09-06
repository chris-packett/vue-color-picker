<template>
    <section class="slider">
        <section class="caption-style">{{ this.caption }}</section>
        <input type="range" min="0" :max="max" v-model="dataValue" v-on:input="updateValue()"/>
    </section>
</template>

<script>
export default {
    name: "slider",
    props: {
        caption: String,
        max: String,
        value: Number,
        valueName:String
    },
    data: function () {
        return {
            dataValue: this.value
        }
    },
    methods: {
        updateValue: function () {
            this.$emit('update-value-event', { 
                value: parseInt(this.dataValue), 
                valueName: this.valueName 
            })
        }
    }
}
</script>

<style>
.hsl-sliders {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.caption-style {
    font-size: .5em;
}
</style>
