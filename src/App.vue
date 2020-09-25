<template>

  <div id="app" >
    <img alt="Vue logo" src="https://tr.rbxcdn.com/38e2b8adf7d7f18731c5aa4efc442f4a/420/420/Decal/Png" height="300px" >
    <Itune />
  </div>

</template>

<script>
import Itune from './components/Itune'

export default {
  name: 'App',
  components: {
    Itune
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
  margin-top: top;
}
body {
  background-color:rgb(50, 50, 50);
  background-size: cover;
}

</style>
