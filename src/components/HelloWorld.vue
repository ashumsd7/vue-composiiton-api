<template>
  <div class="hello">
    <h1>{{ age }}</h1>




    <!-- <h2>{{firstName}}</h2>
    <h2>{{lastName}}</h2> -->


    {{fullName}}

    <button @click="setNewData">change age</button>




    <div class="">

      <!-- v-model  ( no need to use .value here with ref values, just use directly) -->
      <input type="text" placeholder="firstname" v-model="firstName" />
      <input type="text" placeholder="lastname"  v-model="lastName" />
    </div>
  </div>
</template>

<script setup>
import { ref, computed , watch} from "vue";



const age = ref(12);
const firstName = ref("");

const lastName = ref("");

// watch is a function


// takes two params
// 1. dependency of watch : when it will run
// 2. function will run after change value

watch(firstName,function(newVal,oldVal){
  console.log(newVal, oldVal)
})






const fullName =  computed(function(){
  return firstName.value + ' ' + lastName.value
})

function setNewData() {
  age.value = 45;
}

// function setFirstName(event) {
//   firstName.value = event.target.value;
// }

// function setLastName(event) {
//   lastName.value = event.target.value;
// }



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
