<template>
    <div>
        <button @click="decrement">-</button>
        {{ number }}
        <button @click="increment">+</button>
    </div>
</template>

<script>
import { ref } from 'vue'
import useCounter from './helper/counter'

export default {
   setup() {
       const number = ref(0)

       const { increment, decrement } = useCounter(number)

       return {
           number, increment, decrement
       }
   }
}
</script>

<style>

</style>
