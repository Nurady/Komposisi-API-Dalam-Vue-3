<template>
    <div>{{ state.number }}</div>
    <div>{{ user.name }}</div>
    <div>{{ post.title }}</div>
    <div>{{ loading }}</div>
</template>

<script>
import { reactive, ref} from 'vue'


export default {
    setup() {
        const state = reactive({
            number: 0
        })

        const loading = ref(false)
        
        const form = reactive({
            user: {
                name: "Nur",
                username: "adis"
            },
            post: {
                title: "yes",
                body: "ok"
            }
        })

        setTimeout(() => {
            loading.value = true
            form.user.name ="Mya",
            form.post.title ="ohhhh"
        }, 3000);

        setInterval(() => {
          state.number++
        }, 1000);

        return {
            state, ...form, loading
        }
    }
}
</script>

<style>

</style>
