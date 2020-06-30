<template>
  <div>
    <div v-bind:key="index" v-for="(command, index) in commandList">
      <div v-if="reC.test(command)">
        <circleShape
          :size="size"
          :cx="command.split(/\s+/)[1]"
          :cy="command.split(/\s+/)[2]"
          :r="command.split(/\s+/)[3]"
        />
      </div>
      <div v-else-if="reR.test(command)">
        <rectangularShape
          :size="size"
          :x="command.split(/\s+/)[1]"
          :y="command.split(/\s+/)[2]"
          :width="command.split(/\s+/)[3]"
          :height="command.split(/\s+/)[4]"
        />
      </div>
      <div v-else-if="reBlank.test(command)"></div>
      <div v-else-if="reP.test(command)">
        <polygonShape :size="size" :points="command.substr(1)" />
      </div>
      <div v-else>{{addError(index)}}</div>
    </div>
    {{alert()}}
  </div>
</template>

<script>
import circleShape from "./Circle";
import rectangularShape from "./Rectangle";
import polygonShape from "./Polygon";

const errors = [];
export default {
  name: "Output",
  components: {
    circleShape,
    rectangularShape,
    polygonShape
  },
  props: ["commandList"],
  methods: {
    addError(index) {
      errors.push(index + 1);
    },
    alert() {
      if (errors.length > 0) {
        alert(`Error at line: ${errors}.`);
        errors.splice(0, errors.length);
      }
    },
    randomColour() {
      return "#" + Math.floor(Math.random() * 16777215).toString(16);
    }
  },
  data() {
    return {
      size: { height: "250", width: "250" },
      reC: /^[cC]\s+\d+\s+\d+\s+\d+\s*$/,
      reR: /^[rR]\s+\d+\s+\d+\s+\d+\s+\d+\s*$/,
      reP: /^[pP](\s+\d+\s*,\s*\d+\s*){3,}$/,
      reBlank: /^\s*$/
    };
  }
};
</script>

<style scoped>
div {
  position: absolute;
}
</style>