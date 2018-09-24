<template>
  <div id="app">
    <h1>Upload Text</h1>
    <textarea rows="10" v-model="text"></textarea>
    <br>
    <app-upload-text @load="text = $event"></app-upload-text>
  </div>
</template>

<script>
  import UploadText from "./components/UploadText";

  export default {
    name: "app",
    data: () => ({ text: "" }),
    components: {
      "app-upload-text": UploadText
    }
  };
</script>
<style scoped>

  #app {
    text-align: center;
    margin: auto auto;
  }


</style>