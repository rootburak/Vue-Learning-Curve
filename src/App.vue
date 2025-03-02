<template>
    <p ref="showData">{{ showData }}</p>
  <HelloWorld @helloText="handleData" msg="Welcome to Your Vue.js App"/>

</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      showData: ""
    }
  },
  mounted() {
    this.$refs.showData.classList.add("red")
  },
  methods: {  
    handleData(payload) {
      this.showData = payload;
    }
  }
}
</script>

<style>
.red {
  color: red;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
