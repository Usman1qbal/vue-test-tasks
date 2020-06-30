<template>
  <div>
    <svg :height="size.height" :width="size.width">
      <rect :x="x" :y="y" :width="width" :height="height" :fill="colour" />
    </svg>
  </div>
</template>

<script>
export default {
  name: "rectangularShape",
  props: ["size", "x", "y", "width", "height"],
  data() {
    return {
      colour: "#E97126"
    };
  }
};
</script>

<style scoped>
</style>