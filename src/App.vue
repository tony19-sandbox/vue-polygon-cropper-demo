<template>
    <div id="app">
        <polygon-crop :imageSource="require('@/assets/logo.png')" ref="canvas"></polygon-crop>
        <button @click.prevent="crop">Crop</button>
        <button @click.prevent="undo">Undo</button>
        <button @click.prevent="redo">Redo</button>
        <button @click.prevent="reset">Reset</button>

    </div>
</template>
<script>
import VuePolygonCropper from 'vue-polygon-cropper'
export default {
    name: 'App',
    components: {
      'polygon-crop': VuePolygonCropper
    },
    methods: {
        crop: function () {
            this.$refs.canvas.crop();
        },
        undo: function () {
            this.$refs.canvas.undo();
        },
        redo: function () {
            this.$refs.canvas.redo();
        },
        reset: function () {
            this.$refs.canvas.reset();
        }
    }
};
</script>