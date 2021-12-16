<template>
    <div>
        <button @click="decrement">-</button>
        {{ number }}
        <button @click="increment">+</button>
    </div>
    <div>
        <Posts />
    </div>
    <ul v-for="post in posts" :key="post.id">
        <li>{{post.title}}</li>
    </ul>
</template>

<script>
import { onMounted, ref } from 'vue'
import useCounter from './helper/counter'
import Posts from './components/Post.vue'
import axios from 'axios'

export default {
    components: {
        Posts
    },

    setup() {
        const posts = ref([])

        const getPosts = async () => {
            let {data} = await axios.get('https://jsonplaceholder.typicode.com/posts')
            posts.value = data.slice(1,10)
        }

        onMounted(() => {
            getPosts()
        })

        const number = ref(0)

        const { increment, decrement } = useCounter(number)

        return {
            number, increment, decrement, posts
        }
    }
}
</script>

<style>

</style>
