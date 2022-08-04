<template>
  <div class="hello">
    <h1>{{ userName.name }}</h1>
    <h2>{{userName.age}}</h2>


    <h4>{{userAge}}</h4>
  </div>
</template>

<script setup>
//import reactive its work with object only
// it doesn't wrap it with some other .value thing it provides direct object
import {  ref,reactive, isReactive, isRef,toRefs} from "vue";

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


let userAge= ref(12);
// let userName = ref({
// name:'Ashutosh',
// age:122
// });

// reactive works with object only
let userName = reactive({
name:'Ashutosh',
age:122
});



// Object is reactive but not values stored inside


// console.log(userAge, userName)



//isReactive and isRef

// userAge.value is false ( not ref)

console.log(">>>>>>>>isReactive userAge", isRef(userAge.value), userAge.value)
console.log(">>>>>>>>isReactive userName", isReactive(userAge))


// console.log(">>>>>>>>isReactive userName.name", isReactive(userName.name))
// console.log(">>>>>>>>isReactive userName.age", isReactive(userName.age))



// toRefs is used to create object keys values reactive

const userRefs= toRefs(userName)




// How to create nested objetc values reactive


// ref can has object also

setTimeout(() => {
  // console.log(userName.value);
  // userName.name = "s";
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
