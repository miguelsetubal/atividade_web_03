<template>
    <div>
        <div>
        <ul>
            <li v-for="comment in comments" :key="comment.id" v-if="(comment.id % 2) == 0">
                <h4>PostId: {{ comment.postId }} </h4>
                <p>ID: {{ comment.id }} </p>
                <p>Name: {{ comment.name }} </p>
                <p>E-mail: {{ comment.email }} </p>
                <p>Body: {{ comment.body }} </p>
                
            </li>
        </ul>
        </div>
        <button @click="fetchComments">Questão 04</button>
    </div>
</template>

<script>
    export default {
        name: "Comments",
        data() {
        return {
        comments: [],
        baseURI: "https://jsonplaceholder.typicode.com/comments"
        };
    },
    methods: {
        fetchComments: function() {            
            this.$http.get(this.baseURI).then((result) => {
                this.comments = result.data;
                });
            },
        },
    };
</script>