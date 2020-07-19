<template>
  <div id="app">
    <class4 :id="id" :phonenumber="phone" :email="email" :name="name" v-if="visible"></class4>
    <class4
      :id="person.id"
      :phonenumber="person.phone"
      :email="person.email"
      :name="person.name"
      v-for="person in people"
      :key="person.id"
      v-on:disable-card="color='gray'"
      :style="{color:color}"
    ></class4>
    <input type="text" v-model="name" />
    <button v-on:click="toggle">Toggle</button>
  </div>
</template>
<script>
import class4 from "./components/class4";
export default {
  name: "app",

  components: {
    class4
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