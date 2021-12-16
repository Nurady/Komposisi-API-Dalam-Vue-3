<template>
    <div>{{ state.number }}</div>
    <div>{{ user.name }}</div>
    <div>{{ post.title }}</div>
    <div>{{ loading }}</div>
</template>

<script>
import { reactive, toRefs} from 'vue'


export default {
    setup() {
        const state = reactive({
            number: 0
        })

        
        const form = reactive({
            loading: (false),
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
            form.loading = true
            form.user.name ="Mya",
            form.post.title ="ohhhh"
        }, 3000);

        setInterval(() => {
          state.number++
        }, 1000);

        return {
            state, ...toRefs(form)
        }
    }
}
</script>

<style>

</style>
