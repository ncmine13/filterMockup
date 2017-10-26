<template>
  <div id="app">
    <div>Da CUSPIES</div>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
body {
  background-color: #1a1a1a;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: white;
  font-size: 40px;
  font-weight: bolder;
  margin: 5%;
}
</style>
