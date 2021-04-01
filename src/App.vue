<template>
  <div>
    <vue-scroll-snap :fullscreen="true">
      <div id="test1" class="item"></div>
      <div id="test2" class="item"></div>
      <div id="test3" class="item"></div>
      <div id="test4" class="item"></div>
      <div id="test5" class="item"></div>    
    </vue-scroll-snap> 
  </div>
</template>

<script>
import VueScrollSnap from 'vue-scroll-snap'

export default {
  name: 'App',
  components: {
    VueScrollSnap
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
  padding-top: 150px;
  margin: 0 auto;
  width: 800px;
}
#test1 {
  background: #41B813;
}
#test2 {
  background: #35495E;
}
#test3 {
  background: #ff0000;
}
#test4 {
  background: #00ff00;
}
#test5 {
  background: #0000ff;
}
</style>