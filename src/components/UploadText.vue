<template>
    <div class="centerText">
        <label class="upload-text">
            Read File
            <input type="file" @change="loadTextFromFile">
        </label>
    </div>
</template>

<script>
  export default {
    name: "app-upload-text",
    methods: {
      loadTextFromFile(ev) {
        const file = ev.target.files[0];
        const reader = new FileReader();

        reader.onload = e => this.$emit("load", e.target.result);
        reader.readAsText(file);
      }
    }
  };
</script>

<style>
    .upload-text {
        position: relative;
        overflow: hidden;
        display: inline-block;

        /* Fancy button */
        border: 2px solid black;
        border-radius: 5px;
        padding: 8px 12px;
        cursor: pointer;
        margin: 15px;
    }

    .upload-text input {
        position: absolute;
        top: 0;
        left: 0;
        z-index: -1;
        opacity: 0;
    }

</style>
