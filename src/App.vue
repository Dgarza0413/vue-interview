<template>
  <div id="app">
    <CanvasBox />
    <!-- <Modal /> -->
  </div>
</template>

<script>
import CanvasBox from "./components/CanvasBox.vue";
// import Modal from "./components/Modal.vue";
export default {
  name: "App",
  components: {
    CanvasBox,
    // Modal,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin: 0;
  padding: 0;
}
</style>
