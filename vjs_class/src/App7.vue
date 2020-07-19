<template>
  <div id="app">
    <!-- 22th May, 2020 -->
    <!-- Event modifiers -->
    <!-- @ before click is the same as v-on: -->
    <comvmod
    :value="comvmod"
    v-on:input="comvmod=$event">
    <comvmod>
  </div>
</template>
<script>
import class7 from "./components/class7"
export default {
  name: "app",
  components: {
      class7
  },

  data() {
    return {
      comvmod: "",
    };
  },

  methods: {
    toggle: function() {
      this.visible = !this.visible;
    },

    oncex: function() {
      this.number++;
    },
    checked: []
  }
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
.online {
  background-color: green;
}
.default {
  background-color: blue;
}
.offline {
  background-color: gray;
}
.statusbox {
  color: white;
  width: 40px;
  height: 50px;
}
</style>
