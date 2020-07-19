<template>
  <div id="app">
    <!-- <div v-bind:style="{backgroundColor: bgcolor, fontSize: fontsize, border:border}">Hello world!</div> -->
    <div v-bind:style="styles">Hello world!</div>
    <!-- v-show only makes invisible on the dom -->
    <div v-show="visible">Show</div>
    <!-- v-if removes it from the dom completely -->
    <div v-if="visible">If</div>

    <ul>
      <li v-for="(days, index) in days" :key="days">{{index}} {{days}}</li>
    </ul>

    <!-- Object exercise -->
    <ul>
      <li v-for="(seasons, index) in seasons" :key="seasons">{{index}} {{seasons}}</li>
    </ul>
  </div>

  <!-- <div v-for="num in 5" :key="num">{{num}}</div> -->
</template>

<script>
export default {
  name: "app",

  components: {},
  data() {
    return {
      styles: {
        //   bgcolor: "red"
        //   fontsize: "30px",
        //   border: "2px solid black",
        backgroundColor: "red",
        fontSize: "30px",
        border: "2px solid black"
      },
      visible: false,
      //   array
      days: ["Monday", "Tuesday", "Wednesday"],
      //   object
      seasons: {
        name: "Summer",
        age: "Autumn",
        address: "Winter",
        score: "Spring"
      },
      num: 5
    };
  }
};

// import HelloWorld from "./components/HelloWorld.vue";

// export default {
//   name: "App",
//   components: {
//     HelloWorld
//   }
// };
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
