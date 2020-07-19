<template>
  <div id="app">
    <!-- <class5 :id="id" :phonenumber="phone" :email="email" :name="name" v-if="visible"></class5> -->
    <div v-if="visible">
      <class5
        v-for="person in people"
        :key="person.id"
        :person="person"
        v-on:removeCard="toggle"
        :style="{color:color}"
      ></class5>
    </div>
    <input type="text" v-model="name" />
    <button v-on:click="toggle">Toggle</button>
  </div>
</template>
<script>
import class5 from "./components/class5";
export default {
  name: "app",

  components: {
    class5
  },

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
      visible: true
    };
  },

  methods: {
    toggle: function() {
      this.visible = !this.visible;
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