<template>
  <div>
    <svg :height="size.height" :width="size.width">
      <circle :cx="cx" :cy="cy" :r="r" :fill="colour" />
    </svg>
  </div>
</template>

<script>
export default {
  name: "circleShape",
  props: ["size", "cx", "cy", "r"],
  data() {
    return {
      colour: "#FAF130"
    };
  }
};
</script>

<style scoped>
</style>