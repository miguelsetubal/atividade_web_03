<template>
    <div>
        <div>
        <ul>
            <li v-for="user in users" :key="user.userId"  v-if="user.userId == 2 && user.completed == true">
                <h4>UserID: {{ user.userId }} </h4>
                <p>ID: {{ user.id }} </p>
                <p>title: {{ user.title }} </p>
                <p>completed?: {{ user.completed }} </p>
                
            </li>
        </ul>
        </div>
        <button @click="fetchUsers">Questão 02</button>
    </div>
</template>

<script>
    export default {
        name: "Todos",
        data() {
        return {
        users: [],
        baseURI: "https://jsonplaceholder.typicode.com/todos"
        };
    },
    methods: {
        fetchUsers: function() {            
            this.$http.get(this.baseURI).then((result) => {
                this.users = result.data;
                });
            },
        },
    };
</script>