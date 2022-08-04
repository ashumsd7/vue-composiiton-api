<template>
  <div class="hello">
    <!-- <h1>{{ age }}</h1> -->

    <UserData :userName='fullName'  :age='age'/>




    <!-- <h2>{{firstName}}</h2>
    <h2>{{lastName}}</h2> -->


    <!-- {{fullName}} -->

    <button @click="setNewData">change age</button>




    <div class="">

    
      <input type="text" placeholder="firstname" v-model="firstName" />
      <input type="text" placeholder="lastname" ref="lastNameRef" />

       <button @click="setLastName">Set Last Name </button>
    </div>
  </div>
</template>

<script setup>
import UserData from "./UserData.vue";
import { ref, computed , watch} from "vue";

// components:{
//   UserData
// }



const age = ref(12);
const firstName = ref("");

const lastName = ref("");


//creating lastName ref  ( same as ref name in template)
const lastNameRef=  ref(null)

// watch is a function


// takes two params
// 1. dependency of watch : when it will run
// 2. function will run after change value

// watch(firstName,function(newVal,oldVal){
//   console.log(newVal, oldVal)
// })

// more than one watchers

watch([firstName, lastName],function(newValues,oldValues){
  console.log(newValues, oldValues)
})

// newValues, oldValues will get two arrays






const fullName =  computed(function(){
  return firstName.value + ' ' + lastName.value
})

function setNewData() {
  age.value = 45;
}



function setLastName() {
  // lastNameRef is ref with value in template

  lastName.value = lastNameRef.value.value;
  console.log("LAST NAME ENTERED IS",  lastName.value)
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
