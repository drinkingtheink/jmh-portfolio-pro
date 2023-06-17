<template>
  <AppStage />
</template>

<script>
import AppStage from './components/AppStage.vue'

export default {
  name: 'App',
  components: {
    AppStage
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:ital,wght@0,300;0,400;1,300;1,400&family=Quicksand:wght@300;500;600;700&display=swap');

// TYPOG
p, span, a, div {
  font-family: 'Josefin Sans', sans-serif;
}

h1, h2, h3, h4, h5, h6 {
  font-family: 'Quicksand', sans-serif;
}

html, body, ul {
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
}

body {
  padding-bottom: 10rem;
  width: 100vw;
  overflow: hidden;
  overflow-y: scroll;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}

.shaper-ready {
  position: relative;
  height: 100%;
}
</style>
