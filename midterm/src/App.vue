<template>
  <img src="./assets/Todo.png" class="logo" />
  <ul :class="linksClass">
    <li :class="linkClass" v-for="page in pages" :key="page">
    <a href="#" v-on:click.prevent="this.currentPage=page.text">{{page.text}}</a></li>
  </ul>
  <MainPage />
  <DisplayPage v-if="this.currentPage=='Home'"/>
 
</template>

<script>
import MainPage from './components/MainPage.vue'
import DisplayPage from './components/display.vue'


export default {
  name: 'App',
  components: {
    MainPage,
    DisplayPage,
  },
  data(){
    return{
      linkClass: 'link',
      linksClass: 'links',
      pages: [
        {text: 'Home'},
        {text: '|', isLink: false},
        {text: 'Tasks'},
        {text: '|', isLink: false},
        {text: 'Logout'}
      ],
      currentPage: 'Home'
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: #18a1db;
  text-align: center;
  color: #2c3e50;
  margin-top: auto;
  margin-bottom: auto;
  height: 26vh;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    
  }
}

.logo{
  height: 15vh;
  width: 25vh;
}

.links{
  overflow: hidden;
}
.link{
  display: inline-block;
  padding: 15px;
}
</style>
