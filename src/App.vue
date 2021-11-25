<template>
   <div id="app">
      <GoogleMap />
   </div>
</template>
 
<script>
import GoogleMap from "./components/GoogleMap";
 
export default {
  name: 'App',
  components: {
  GoogleMap
}
}
</script>
 
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  margin-top: 50px;
}
</style>