<template>
    <div>{{ name }}</div>
</template>

<script>
import { ref } from 'vue'


export default {
    setup() {
        const name = ref("Adis")

        setTimeout(() => {
            name.value = "izzan"
        }, 1000)

        return {
            name
        }
    }
}
</script>

<style>

</style>
