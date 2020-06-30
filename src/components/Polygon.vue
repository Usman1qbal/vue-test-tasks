<template>
  <div>
    <svg :height="size.height" :width="size.width">
      <polygon :points="points" :fill="colour" />
    </svg>
  </div>
</template>

<script>
export default {
  name: "polygonShape",
  props: ["size", "points"],
  data() {
    return {
      colour: "#89999F"
    };
  }
};
</script>

<style scoped>
</style>