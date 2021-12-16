<template>
    <div>{{ name }}</div>
    <div>{{ number }}</div>
</template>

<script>
import { ref } from 'vue'


export default {
    setup() {
        const name = ref("Adis")
        const number = ref(0)

        setTimeout(() => {
            name.value = "izzan"
            
        }, 1000)

        setInterval(() => {
          number.value++
        }, 1000);

        return {
            name, number
        }
    }
}
</script>

<style>

</style>
