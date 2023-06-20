<script setup>
import Header from './components/header.vue'
import Form from './components/form copy.vue'
</script>

<template>
  <div>
    <Header />
    <RouterView />
    <Form />
  </div>
</template>

<style>
*{
  box-sizing: border-box;
  font-family: sans-serif;

}
body{
  margin: 0;
  padding: 0;
  place-items:unset;
}
#app{
  display: block;
  max-width: none;
  width: 100%;
  padding: 0;
}
li{
  list-style: none;
}
a{
  text-decoration: none;
}
a:hover{
  background-color: unset;
}
</style>
