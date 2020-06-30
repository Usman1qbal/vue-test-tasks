<template>
  <div id="app">
    <label><strong>Vue Test Task</strong></label><br/>
    <div class="grid-container">
      <div class="grid-item">
        <textarea v-model="shapeCoordinate" placeholder="Enter Coordinates"></textarea>
        <button v-on:click="commandList=shapeCoordinate.split('\n')">Shape Design</button>
      </div>
      <div class="grid-item">
        <Output :commandList="commandList" />
      </div>  
    </div>
  </div>
</template>

<script>
import Output from "./components/Output";

export default {
  name: "app",
  components: {
    Output
  },
  methods: {
    reader() {
      this.test = this.circle.cx.split("\n");
    }
  },
  data() {
    return {
      shapeCoordinate: ``,
      commandList: []
    };
  }
};
</script>

<style>
body {
  background: black;
  padding-top: 200px;
  display: flex;
  justify-content: center;
}

textarea {
    margin: 0px;
    width: 426px;
    height: 256px;
    border-width: 19px;
    border-radius: 27px;
    font-family: sans-serif;
}
label{
    color: white;
    font-size: 4rem;
    margin: 35rem;
}
button {
  display: block;
  margin: 10px auto 20px;
  padding: 15px 50px;
  font-size: 24px;
  cursor: pointer;
  text-align: center;
  text-decoration: none;
  outline: none;
  color: #fff;
  background-color: blue;
  border: none;
  border-radius: 15px;
}

button:hover {
  background-color: blue;
}

button:active {
  background-color: blue;
}
.grid-container {
  display: grid;
  grid-template-columns: 54rem 40rem;
  padding: 10px;
}
.grid-item {
  padding: 20px;
  font-size: 30px;
  text-align: center;
}
</style>
