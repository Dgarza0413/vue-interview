<template>
  <div>
    <span
      class="box"
      :style="style"
      v-on:click="handleClick"
      v-on:mouseover="mouseOver"
      v-on:mouseleave="mouseLeave"
      >box</span
    >
    <modal-view
      ref="modal"
      v-if="modal"
      :sku="sku"
      :name="name"
      :display="display"
      :size="size"
      :position="position"
      :show="display"
    ></modal-view>
  </div>
</template>

<script>
import ModalView from "./Modal.vue";

export default {
  name: "BoxSelection",
  components: {
    ModalView,
  },
  props: {
    id: String,
    sku: String,
    position: String,
    name: String,
    x: String,
    y: String,
    size: String,
    color: String,
  },
  computed: {
    style: function () {
      return {
        "border-color": this.hovering ? this.color : "red",
        left: this.x + "px",
        top: this.y + "px",
      };
    },
  },
  data: function () {
    return {
      modal: false,
      hovering: false,
      display: false,
    };
  },
  methods: {
    mouseOver: function () {
      this.hovering = true;
    },
    mouseLeave: function () {
      this.hovering = false;
    },
    handleClick: function () {
      const data = this.$options.propsData;
      console.log(data);
      this.display = true;
      this.modal = true;
      // console.log(this.$refs.ModalView.style.display);
      // let modalView = this.$refs.ModalView.style;
      // modalView = "inline";
    },
  },
};
</script>

<style scoped>
.box {
  position: absolute;
  border: black 1px dotted;
  transform: translate(-50%, -50%);
}
</style>