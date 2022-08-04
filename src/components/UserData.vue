<template>
    <div>
<h1>{{userName}} is  {{age}} years old</h1>

<button @click="emitSomething">emitSomething</button>
    </div>
</template>

<script setup>
import {  defineProps, defineEmits} from "vue";

const props = defineProps({
    userName:String,
    age:Number
})


const emit = defineEmits(['change'])

function emitSomething(){
let platform ='twitter'
    emit('change', platform)

}

console.log(props)
</script>

<style lang="scss" scoped>

</style>