<template>
  <div id="app">
    <timeline ref="timeline" :items="items" :groups="groups" :options="options">
    </timeline>
  </div>
</template>

<script>
import { Timeline, DataSet } from "vue2vis";
import "vue2vis/dist/vue2vis.css";

export default {
  name: "App",
  components: {
    Timeline,
  },
  methods: {},
  data() {
    return {
      groups: new DataSet([
        {
          id: 0,
          content: "Software",
        },
        {
          id: 1,
          content: "Chip Level",
        },
        {
          id: 2,
          content: "Critical",
        },
        {
          id: 3,
          content: "Testing",
        },
      ]),
      items: new DataSet([
        {
          id: 0,
          group: 2,
          start: new Date(),
          content: "",
        },
      ]),
      options: {
        orientation: "top",
        type: "point",
      },
    };
  },
  created() {},
  mounted() {
    var horizontalLine = document.createElement("div");
    horizontalLine.className = "horizontal-line";
    var container = document.querySelector(".vis-vertical");
    container.appendChild(horizontalLine);
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.horizontal-line {
  position: absolute;
  width: 100%;
  height: 2px;
  background: #2c3e50;
  z-index: 1;
  top: 130px;
}
</style>
