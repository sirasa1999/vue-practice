<template>
    person's name = {{props.name}} <br>
    person's age = {{props.age}}<br>
    person's address = {{props.address}}<br>
    <!-- {{name}} {{age}} {{address}} -->
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  name: {type: String, default:"Ram"},
  age: {type:Number, default:20},
  address: {type: String, default:"Ayodhya"}
})

</script>