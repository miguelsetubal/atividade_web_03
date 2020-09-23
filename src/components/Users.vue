<template>
    <div>
        <div>
        <ul>
            <li v-for="user in users" :key="user.id"  v-if="user.id < 6">
                <h4> {{user.id}} {{ user.name }} </h4>
                <p>E-mail: {{ user.email }} </p>
                <p>User Name: {{ user.username }} </p>
                <p>Endereço:{{user.address.street}}, {{user.address.suite}} - {{user.address.city}} - {{user.address.zipcode}} </p>
                <p>Geolocalização: lat:{{user.address.geo.lat}} | lng:{{user.address.geo.lng}}</p>
                <p>Phone: {{user.phone}}</p>
                <p>website: {{user.website}}</p>
                <p>company: {{user.company.name}}, {{user.company.catchPhrase}}, {{user.company.bs}}</p>
                
            </li>
        </ul>
        </div>
        <button @click="fetchUsers">Questão 01</button>
    </div>
</template>

<script>
    export default {
        name: "Users",
        data() {
        return {
        users: [],
        baseURI: "https://jsonplaceholder.typicode.com/users"
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