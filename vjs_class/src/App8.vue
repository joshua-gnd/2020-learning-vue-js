<template>
  <div id="app">
    <!-- <li v-for="country in countries" :key="country.country_code">{{country.country_name}}</li> -->

    <!-- Using Ele.io -->
    <el-select v-model="selected" placeholder="Select">
      <el-option
        v-for="country in countries"
        :key="country.country_code"
        :label="country.country_name"
        :value="country.country_name"
      ></el-option>
    </el-select>
    {{selected}}
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "app",
  components: {},
  data() {
    return {
      countries: [],
      selected: "Grenada"
    };
  },
  mounted() {
    this.getCountries();
  },
  methods: {
    async getCountries() {
      let response = await axios.get("http://159.65.170.90:3009/api/countries");
      console.log(response);
      this.countries = response.data.data;
    }
  }
};
</script >

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
