<template>
    <div>
        <div>
        <ul>
            <li v-for="post in posts" :key="post.id" v-if="(post.id % 2) != 0">
                <h4>PostId: {{ post.postId }} </h4>
                <p>ID: {{ post.id }} </p>                
                <p>Title: {{ post.title }} </p>
                <p>Body: {{ post.body }} </p>
                
            </li>
        </ul>
        </div>
        <button @click="fetchPosts">Questão 05</button>
    </div>
</template>

<script>
    export default {
        name: "Posts",
        data() {
        return {
        posts: [],
        baseURI: "https://jsonplaceholder.typicode.com/posts"
        };
    },
    methods: {
        fetchPosts: function() {            
            this.$http.get(this.baseURI).then((result) => {
                this.posts = result.data;
                });
            },
        },
    };
</script>