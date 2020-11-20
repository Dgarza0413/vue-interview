<template>
  <div class="canvas-overlay">
    <img src="../assets/polaris-280-parts-diagram.jpg" />
    <canvas ref="canvas"></canvas>
    <selection
      v-for="item in data"
      v-bind:key="item.id"
      :position="item.key"
      :sku="item.sku"
      :name="item.name"
      :x="item.x"
      :y="item.y"
      :size="item.size"
      :color="item.color"
    ></selection>
  </div>
</template>

<script>
import data from "../data/data.json";
import Selection from "./Selection.vue";
export default {
  components: { Selection },
  name: "CanvasBox",
  data() {
    return {
      data: data,
      showModal: false,
    };
  },
  methods: {
    // draw() {
    //   let c = this.$refs["canvas"];
    //   const canvas = c.getContext("2d");
    //   canvas.beginPath();
    //   canvas.rect(20, 20, 150, 100);
    //   canvas.stroke();
    //   console.log(canvas);
    // },
  },
};
</script>

<style scoped>
canvas {
  position: absolute;
  left: 0;
  /* height: 100%; */
  /* width: 100%; */
}

.canvas-overlay {
  /* position: relative; */
  /* height: 2000px; */
  /* background-image: url("../assets/polaris-280-parts-diagram.jpg"); */
  /* background-repeat: no-repeat; */
  /* background-position: center; */
}
</style>