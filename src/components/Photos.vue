<template>
    <div>
        <div>
            <ul>
            <li v-for="photo in photos" :key="photo.id"  v-if="photo.albumId == 3">
                <img v-bind:src="photo.url">             
            </li>
        </ul>
        </div>
        <button @click="fetchPhotos">Questão 03</button>
    </div>
</template>

<script>
    export default {
        name: "Photos",
        data() {
        return {
        photos: [],
        baseURI: "https://jsonplaceholder.typicode.com/photos"
        };
    },
    methods: {
        fetchPhotos: function() {            
            this.$http.get(this.baseURI).then((result) => {
                this.photos = result.data;
                });
            },
        },
    };
</script>