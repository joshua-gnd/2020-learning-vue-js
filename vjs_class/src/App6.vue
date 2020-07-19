<template>
  <div id="app">
    <!-- 20th May, 2020 -->
    <!-- Event modifiers -->
    <!-- @ before click is the same as v-on: -->
    <button @click.once="oncex">oncex</button>

    <div>
      <button></button>
    </div>
    {{number}}
    <a href="https://youtu.be/NHHhiqwcfRM" @click.prevent>a youtube vid</a>

    <!-- exercise  display checked names in a list-->

    <input type="checkbox" id="jack" value="Jack" v-model="checkedNames" />
    <label for="jack">Jack</label>
    <input type="checkbox" id="john" value="John" v-model="checkedNames" />
    <label for="john">John</label>
    <input type="checkbox" id="mike" value="Mike" v-model="checkedNames" />
    <label for="mike">Mike</label>
    <br />
    <span>Checked names: {{ checkedNames }}</span>

    <li v-for="item in checked" :key="item"></li>
    {{item}}
  </div>
</template>
<script>
export default {
  name: "app",

  data() {
    return {
      id: "d764384",
      phone: 839475,
      name: "john jones",
      email: "cardel@sonover.com",
      people: [
        {
          id: "P1ID",
          phone: 839475,
          name: "Shineeva Chivette",
          email: "cardel@sonover.com"
        },
        {
          id: "P2ID",
          phone: 839475,
          name: "Mr. Man",
          email: "cardel@sonover.com"
        }
      ],
      visible: true,
      number: 1
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
