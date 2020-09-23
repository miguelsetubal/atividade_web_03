<template>
  <div id="app">
    <h2>Atividade Remota de WEB 03</h2>
    <h3><strong>Nome: </strong> Miguel Jonas Lima Setúbal</h3>
    <h3><strong>Matricula: </strong>415043</h3>    
    <Users/>
    <Todos/>
    <Photos/>
    <Comments/>
    <Posts/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Users from './components/Users.vue'
import Todos from './components/Todos.vue'
import Photos from './components/Photos.vue'
import Comments from './components/Comments.vue'
import Posts from './components/Posts.vue'
export default {
  name: 'App',
  components: {
    Users,
    Todos,
    Photos,
    Comments,
    Posts
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
