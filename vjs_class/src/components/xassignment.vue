<template>
<div class="hellowrld">

<h1>{{name}}</h1>
<p>{{phone}}</p>
<p>{{email}}</p>
<p>{{address}}</p>

</div>
</template>

<script>
export default {
  name: 'assignment',
  props:{
    name: String,
    phone: String,
    email: String,
    address: String,

  }

  
}

</script>






<style scoped>
.hellowrld{
  padding:10px;
  background-color:white;
  width:25%;
display:inline-block;
  color:gray;
  border-radius:10px;
  border:2px solid rgb(180, 180, 180);
  margin:10px;

  
 
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
