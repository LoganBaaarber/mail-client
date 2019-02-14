<template>
  <div id="app">

    <img style="height:35%; width:35%;margin-bottom:5%;" alt="mail logo" class="img-fluid" src="./assets/mail.svg">
    <JoinList/>
  </div>
</template>

<script>
import JoinList from './components/JoinList.vue'

export default {
  name: 'app',
  components: {
    JoinList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
