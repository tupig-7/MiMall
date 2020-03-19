<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
// import axios from "axios";
import jsonp from "jsonp";
export default {
  name: "App",
  components: {
    HelloWorld
  },
  data() {
    return {
      data: ""
    };
  },
  mounted() {
    let url =
      "/api/pay/cartorder?jsonpcallback=jQuery19107668782984683105_1584631429107&_=1584631429108";
    // axios.get(url).then(() => {});
    jsonp(url, (err, res) => {
      let result = res;
      this.data = result;
    });
  }
};
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
</style>
