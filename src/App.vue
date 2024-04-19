<template>
  <TheHeader
    v-if="showHeader"
  />

  <div v-show="ShowName">
    Nome: {{  firstName  }} <br>
    Sobrenome: {{ lastName }}
  </div>

  <div v-if="accessLevel === 'admin'" >Admin</div>
  <div v-else-if="accessLevel === 'marketing'" >Marketing</div>
  <div v-else >User</div>

<div>
  <p v-for="(item, index) in todos" v-bind:key="item.id" class="todos-item">
  {{ index }} - {{ item.title }}
  </p>
</div>

  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TheHeader from './components/TheHeader.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    TheHeader
  },
  data(){
    return{
      showHeader: true,
      firstName: 'Jhon',
      lastName: 'Snow',
      ShowName: false,
      accessLevel: 'admin',
      todos: [
              {
              "userId": 1,
              "id": 1,
              "title": "delectus aut autem",
              "completed": false
              },
              {
              "userId": 1,
              "id": 2,
              "title": "quis ut nam facilis et officia qui",
              "completed": false
              },
              {
              "userId": 1,
              "id": 3,
              "title": "fugiat veniam minus",
              "completed": false
              },
              {
              "userId": 1,
              "id": 4,
              "title": "et porro tempora",
              "completed": true
              },
              {
              "userId": 1,
              "id": 5,
              "title": "laboriosam mollitia et enim quasi adipisci quia provident illum",
              "completed": false
              }
              ]
    }
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
.todos-item{
  background: #000;
  margin: 0 0 5px 0;
  padding: 3px 6px;
  color: #fff;
}
</style>
