<template>
  <div id="app">
    <full-page :options="options" id="fullpage">
        <div class="section">
            <h3>Section 1</h3>
        </div>
        <div class="section">
            <h3>Section 2</h3>
        </div>
    </full-page>  
  </div>
</template>

<script>

export default {
  name: 'App',
  // components: {
  //   HelloWorld
  // }
  data () {
      return {
        options: {
          licenseKey: 'YOUR_KEY_HERE',
          afterLoad: this.afterLoad,
          scrollOverflow: true,
          scrollBar: false,
          menu: '#menu',
          navigation: true,
          anchors: ['page1', 'page2', 'page3'],
          sectionsColor: ['#41b883', '#ff5f45', '#0798ec', '#fec401', '#1bcee6', '#ee1a59', '#2c3e4f', '#ba5be9', '#b4b8ab']
        }
      }
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
</style>
