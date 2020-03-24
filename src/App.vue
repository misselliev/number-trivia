<template>
  <div id="app">
    <full-page :options="options" id="fullpage" v-if="isLoaded">
      <div v-for="fact in trivia" :key="fact" class="section">
        <div class="container">
          <img src="./assets/robot.png" alt="shower icon" />
          <p>Random number fact:</p>
          <p class="quote">{{ fact }}</p>
          <p class="link">
            More facts like this
            <a href="http://numbersapi.com/">here</a>
          </p>
        </div>
      </div>
    </full-page>
  </div>
</template>

<script>
export default {
  name: "App",
  created() {
    let a = Math.floor(Math.random() * 30);
    let b = Math.floor(Math.random() * 30);
    let min, max;
    if (a > b) {
      max = a;
      min = b;
    } else {
      min = a;
      max = b;
    }
    fetch(`http://numbersapi.com/${min}..${max}`)
      .then(response => response.json())
      .then(data => {
        this.trivia = data;
        this.isLoaded = true;
      });
  },
  data() {
    return {
      isLoaded: false,
      trivia: [],
      options: {
        licenseKey: "YOUR_KEY_HERE",
        scrollBar: true,
        sectionsColor: [
          "#41b883",
          "#ff5f45",
          "#0798ec",
          "#fec401",
          "#1bcee6",
          "#ea2a",
          "#ba5be9",
          "#b4b8ab",
          "#41b883",
          "#ff5f45",
          "#0798ec",
          "#fec401",
          "#1bcee6",
          "#ee1a59",
          "#ba5be9",
          "#b4b8ab",
          "#41b883",
          "#ff5f45",
          "#0798ec",
          "#fec401",
          "#1bcee6",
          "#ee1a59",
          "#ba5be9",
          "#b4b8ab",
          "#41b883",
          "#ff5f45",
          "#0798ec",
          "#fec401"
        ]
      }
    };
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@1,600&display=swap");

#app {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body {
  margin: 0;
  padding: 0;
}
.container {
  margin: auto;
  max-width: 800px;
  padding: 80px 16px;
}

.section {
  text-align: center;
}

.quote-symbol {
  font-size: 64px;
  line-height: 0;
  margin-top: 50px;
  color: white;
}

.quote {
  color: black;
  font-size: 36px;
  line-height: 1.5;
}

img {
  height: 12em;
  width: 12em;
  border-radius: 50%;
}

p {
  font-size: 1.5em;
}

.link {
  margin-top: 2em;
  text-align: right;
}
</style>
