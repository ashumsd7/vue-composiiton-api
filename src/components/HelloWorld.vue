<template>
  <div class="hello">
    <h1>{{ userName }}</h1>
  </div>
</template>

<script setup>
import { ref } from "vue";
// ref is a function || create reference not only dom reference but reactive values ( creates values)

// name: "HelloWorld",
// data() {
//   return {
//     property: 'value',
//   };
// },

// set is created and run very early, you will not get access of props and methods

// ref is for reactive
// ref creates a object with value property

let userName = ref("Ashu");

setTimeout(() => {
  console.log(userName.value);
  userName.value = "s";
}, 2000);

// in setup always return a object
// return { x:userName}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
