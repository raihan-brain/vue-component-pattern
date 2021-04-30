<template>
  <ul class="list-group list-group-horizontal">
    <li class="list-group-item">{{ image }}</li>
    <li class="list-group-item">{{ title }}</li>
    <li class="list-group-item">{{ length }}</li>
    <li class="list-group-item">{{ haveSeenMovie }}</li>
  </ul>
  <slot name="reference"></slot>
  <slot name="hero" :logo="logoImage"></slot>
  <slot></slot>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "MovieComponent",
  props: {
    image: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
      validator: (propValue: string) => {
        const valid = propValue.length > 1;
        console.log("=========" + propValue.length + valid);
        return valid;
      },
    },
    length: {
      type: [Number, String],
      default: 90,
    },
    haveSeenMovie: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      logoImage: "Harry potter!!",
    };
  },
});
</script>
<style scoped></style>
