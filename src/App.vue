<template>
  <img alt="logo" src="./assets/logo-highday-600x600.png">
  <h2>{{title}}</h2>
  
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      title: 'My first Vue :0-'
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
  color: #063be7;
  margin-top: 100px;
}
img {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 50%;
  height: 50px;
  width: 50px;
  border-radius: 100%;
}
</style>
