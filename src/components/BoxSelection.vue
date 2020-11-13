<template>
  <span class="box" :style="style" @mouseover="mouseOver">{{ name }}</span>
</template>

<script>
export default {
  name: "BoxSelection",
  props: {
    id: String,
    sku: String,
    name: String,
    x: String,
    y: String,
    size: String,
    color: String,
  },
  computed: {
    style: function () {
      return "background-color: " + this.hovering ? this.color : "yellow";
    },
  },
  data: function () {
    return {
      hovering: false,
    };
  },
  methods: {
    mouseOver: function () {
      console.log("hovered");
      this.hovering = !this.hovering;
      console.log(this.hovering);
    },
  },
};
</script>

<style scoped>
.box {
  position: absolute;
  border: black 1px dotted;
}
</style>