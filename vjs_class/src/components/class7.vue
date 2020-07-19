<template>
  <div class>
    <input v-bind:value="value" v-on:input="$emit('input', $event.target.value)" />
  </div>
</template>

<script>
export default {
  props: ["value"]
};
</script>

<style scoped>
/* .class7 {
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
} */
</style>