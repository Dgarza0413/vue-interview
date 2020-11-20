<template>
  <div :style="styled" ref="modal" id="modal">
    <button v-on:click="exit" id="exit-button">X</button>
    <h1>Product Info</h1>
    <div>sku {{ sku }}</div>
    <div>name {{ name }}</div>
    <div>size {{ size }}</div>
    <div>position {{ position }}</div>

    <button>Submit</button>
  </div>
</template>

<script>
export default {
  name: "modal",

  props: {
    id: String,
    sku: String,
    name: String,
    position: String,
    x: String,
    y: String,
    size: String,
    color: String,
    show: Boolean,
  },

  methods: {
    exit: function () {
      this.close = false;
      this.displayModal = true;
    },
  },
  computed: {
    styled: function () {
      return {
        display: this.close === true ? "inline" : "none",
      };
    },
  },
  data: function () {
    return {
      close: this.show,
      displayModal: false,
    };
  },
};
</script>

<style>
#modal {
  position: absolute;
  background-color: white;
  left: 50%;
  top: 0%;
  transform: translate(-50%, 50%);
  border: 1px solid black;
  height: 500px;
  width: 500px;
  z-index: 1;
}
#exit-button {
  position: absolute;
  right: 20px;
  top: 20px;
}
</style>