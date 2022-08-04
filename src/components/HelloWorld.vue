<template>
  <div class="hello">
    <h1>{{ age }}</h1>

    <button @click="setNewData">change age</button>
  </div>
</template>

<script setup>
import { ref } from "vue";

const age = ref(12);





function setNewData(){
     age.value=45
}

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
