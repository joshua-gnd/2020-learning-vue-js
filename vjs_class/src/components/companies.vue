<template>
  <div id="card">
    <h1>{{ company.name }}</h1>
    <h3>{{ company.address }}</h3>
    <p>{{ company.phone }} || {{ company.email }}</p>
    <slot name="slot1"></slot>
  </div>
</template>

<script>
export default {
  props: ["company"],
};
</script>

<style>
#card {
  display: block;
  margin: 1rem auto;
  border: 2px solid #800020;
  border-radius: 12px;
  padding: 0 2rem 1rem;
  width: 300px;
  color: #800020;
  background-color: #ffc0d0;
  font-family: Helvetica, sans-serif;
  text-align: center;
}
</style>
