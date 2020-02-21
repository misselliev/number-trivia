<template>
  <div id="app">
    <full-page :options="options" id="fullpage">
        <div class="section">
          <div class="container">
            <img alt="hashtag">
            <div class="quote-symbol">"</div>
            <p class="trivia">Fact goes here</p>
          </div>
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
body {
  margin:0;
  padding: 0;
}
.container{
  margin: auto;
  max-width: 800px;
  padding: 80px 16px;
}

.section{
  text-align: center;
}

.quote-symbol{
  font-size: 64px;
  line-height: 0;
  margin-top: 50px;
  color: white;
}

.quote{
  color: pink;
  font-size: 36px;
  line-height: 1.5;  
}

</style>
