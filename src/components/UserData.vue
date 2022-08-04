<template>
    <div>
<h1>{{userName}} is  {{age}} years old</h1>
    </div>
</template>

<script setup>
import {  defineProps} from "vue";

const props = defineProps({
    userName:String,
    age:Number
})

console.log(props)
</script>

<style lang="scss" scoped>

</style>