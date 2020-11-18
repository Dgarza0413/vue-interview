<template>
  <div :style="styled" ref="modal" id="modal">
    <div>This is a model on click</div>
    <button v-on:click="exit" id="exit-button">X</button>
  </div>
</template>

<script>
export default {
  name: "modal",

  methods: {
    exit: function () {
      this.displayModal = false;
    },
  },
  computed: {
    styled: function () {
      return {
        display: this.displayModal ? "inline" : "none",
      };
    },
  },
  data: function () {
    return {
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
}
#exit-button {
  position: absolute;
  right: 20px;
  top: 20px;
}
</style>