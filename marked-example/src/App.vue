<template>
  <div id="app">
  <textarea v-model="markdown" cols="40" rows="15"></textarea>
    <div v-html="markdown2Html"></div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

import { marked } from 'marked';

export default {
  name: 'App',
  components: {
    // HelloWorld
  },
  data() {
    return {
      markdown: 
      `# Hello World\n\n**bold**\n*italics*\n## Subsection`
    }
  },
  computed: {
    markdown2Html() {
      return marked(this.markdown)
    }

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
