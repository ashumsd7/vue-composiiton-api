<template>
  <div class="hello">
    <h1>{{ age }}</h1>




    <!-- <h2>{{firstName}}</h2>
    <h2>{{lastName}}</h2> -->


    {{fullName}}

    <button @click="setNewData">change age</button>




    <div class="">
      <input type="text" placeholder="firstname" @input="setFirstName" />
      <input type="text" placeholder="lastname" @input="setLastName" />
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

// computed is a function

const age = ref(12);
const firstName = ref("");

const lastName = ref("");




// fullName is a computed property
// fullName is also a ref , computed values are also reactive but only read only
const fullName =  computed(function(){
  return firstName.value + ' ' + lastName.value
})

function setNewData() {
  age.value = 45;
}

function setFirstName(event) {
  firstName.value = event.target.value;
}

function setLastName(event) {
  lastName.value = event.target.value;
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
