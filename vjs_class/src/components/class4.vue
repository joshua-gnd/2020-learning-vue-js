<template>
  <div class="class4">
    <div>{{id}}</div>
    <h1>{{name}}</h1>
    <h2>{{phonenumber}}</h2>
    <p>{{email}}</p>
    <br />
    <button v-on:click="$emit('disable-card')">disable</button>
  </div>
</template>
<script>
export default {
  name: "class4",
  props: {
    id: String,
    name: String,
    phonenumber: Number,
    email: String
  }
};
</script>
<style scoped>
.class4 {
  padding: 10px;
  background-color: rgb(180, 180, 180);
  width: 30%;
  margin: auto;
  color: white;
  border-radius: 10px;
  margin-top: 10px;
}
h3 {
  margin: 20px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>