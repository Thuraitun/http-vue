<template>
    <!-- <button @click="getPosts">Loading Posts</button> -->
    <h3 v-if="errMsg">{{ errMsg }}</h3>
    <div v-for="post in posts" :key="post.id">
        <h4>{{ post.id }} {{ post.title }}</h4>
        <p>{{ post.body }}</p>
        <hr>
    </div>
</template>

<script>
    import axios from 'axios';

    export default {
        name: 'PostList',
        created() {
            this.getPosts()
        },
        data() {
            return {
                posts: [],
                errMsg: '',
            }
        },
        methods: {
            getPosts() {
                axios
                .get('https://jsonplaceholder.typicode.com/posts')
                .then((response) => {
                    console.log(response.data)
                    this.posts = response.data
                })
                .catch((error) => {
                    console.log(error)
                    this.errMsg = 'Error retrieving data'
                })
            }
        }
    }
</script>

<style scoped>
    div{
        text-align: center;
    }
    h4{
        color: blue;
    }
    h3{
        color: red;
    }
</style>