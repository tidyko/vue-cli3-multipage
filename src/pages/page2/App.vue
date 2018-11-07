<template>
  <div id="app">
    <a href="/">index</a> | <a href="/page1.html">page1</a> | <a href="/page2.html">page2</a>
    <h2>this is page2 index page</h2>
    <a @click="test1">test1</a>
  </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue'
//axios
import Vue from 'vue'
Vue.prototype.$http = api

export default {
  name: 'app',
  components: {
    HelloWorld
  },methods:{
    test1: function(){
      this.$http.get({
      type: 'json', baseUrl: 'http://localhost:8080/api', api: '/demo'},
      null,
      response=>{
        console.log("response")
        console.log(response)
      },
      error=>{
        console.log("error")
        console.log(error[0])
      });
    }
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
