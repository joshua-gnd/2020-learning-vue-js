<template>
<div class="hellowrld" >
<div>{{employee.employeeid}}</div>
<h1>{{employee.name}}</h1>
<h2>{{employee.phone}}</h2>
<p>{{employee.email}}</p><br>
<button v-on:click="$emit('remove-card','red')">remove</button><br>


</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: ['employee']
  
}

</script>


<style scoped>
.hellowrld{
  padding:10px;
  background-color:rgb(180, 180, 180);
  width:30%;
  margin:auto;
  color:white;
  border-radius:10px;
  margin-top:10px
 
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
