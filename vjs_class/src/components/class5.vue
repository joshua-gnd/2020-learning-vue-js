<template>
  <div class="class5">
    <div>{{person.id}}</div>
    <h1>{{person.name}}</h1>
    <h2>{{person.phonenumber}}</h2>
    <p>{{person.email}}</p>
    <br />
    <button v-on:click="$emit('removeCard')">remove</button>
  </div>
</template>
<script>
export default {
  name: "class5",
  props: ["person"]
};
</script>
<style scoped>
.class5 {
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