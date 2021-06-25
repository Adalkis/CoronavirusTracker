<template>
  <div id="app">
       <logo/>
     <link rel="stylesheet" 
        href="https://use.fontawesome.com/releases/v5.2.0/css/all.css" 
        integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ" 
        crossorigin="anonymous">
 
    <trackingcovid/>
  </div>
</template>

<script>
import trackingcovid from './components/trackingcovid.vue'
import logo from './components/logo.vue'

export default {
  name: 'App',
  components: {
    trackingcovid,
    logo
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
html{
  background: #F8E3D2;
}
</style>
