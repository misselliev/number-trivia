<template>
  <div id="app">
    <full-page :options="options" id="fullpage" v-if="isLoaded">
      <div v-for="fact in trivia" :key="fact" class="section">
          <div class="container">
            <img src="./assets/robot.png" alt="shower icon">
            <p class="quote"><a :href="fact.text">{{ fact.text }}</a></p>
          </div>
      </div>
  </full-page>
  </div>
</template>

<script>

export default {
  name: 'App',
  created() {
    fetch('http://numbersapi.com/random?json')
      .then(response => response.json())
      .then(data => {
        console.log(data)
        this.trivia = data.text
        this.isLoaded = true
      })
  },
  data () {
      return {
        isLoaded: false,
        trivia: [],
        options: {
          scrollBar: true,
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

img{
  height: 10em;
  width: 10em;
  border-radius: 50%;
}

</style>
