<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org"
           target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org"
           target="_blank">Forum</a></li>
      <li><a href="https://chat.vuejs.org"
           target="_blank">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs"
           target="_blank">Twitter</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/"
           target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/"
           target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/"
           target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue"
           target="_blank">awesome-vue</a></li>
    </ul>

    <button @click="getChildrenFunction">按钮</button>

    <test-panel ref="panel"></test-panel>
    <test-toast ref="toast"></test-toast>

  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      testArr: [1, 2, 6]
    }
  },
  created () {
    console.log('====================================');
    console.log(this.$myMethod(this.testArr));
    console.log('====================================');
    this.$nextTick(() => {
      console.log('====================================');
      console.log(this.$refs.panel.$el);
      console.log('====================================');
    })
  },
  methods: {
    getChildrenFunction () {
      this.$nextTick(() => {
        this.$refs.toast.toastPlugin('在父组件里触发调用的toast', 2500)
      })
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
