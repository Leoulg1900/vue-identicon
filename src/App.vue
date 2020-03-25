<template>
  <div id="app">
    <div>
      input:
      <input @input="generateIdenticon" type="text" />
    </div>
    <div>
      output:
      <div v-html="identicons"></div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
const jdenticon = require("jdenticon");

export default {
  name: "App",
  data() {
    //initilize our state
    return {
      textInput: ""
    };
  },
  computed: {
    identicon() {
      return jdenticon.toSvg(this.textInput, 200);
    }
  },
  methods: {
    //
    generateIdenticon(event) {
      this.textInput = event.target.value;
      // console.log(event.target.value);
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
