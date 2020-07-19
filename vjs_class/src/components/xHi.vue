<template>


<div id="a">


      <slot name="slot2"></slot>
  <H1 >{{message}}</H1>
   <H1 >{{displayNumber}}</H1>
   <slot name="slot1"></slot>
   

 

  
  </div>
</template>


<script>
export default {
  name:'h',

props:{
message:{
  required:true,

  type:[String, Number],


},

displayNumber:{
  required:true,
default:1000


}

}
  


  
 


}
</script>

<style scoped>
#a{
  background-color: red;
}
</style>