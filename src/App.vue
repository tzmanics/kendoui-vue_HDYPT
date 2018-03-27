<template>
  <div id="app">
    <h1> H D Y P T </h1>
    <h4> a site that asks, 'How do you pronounce that?' </h4>
    <term-list></term-list>
  </div>
</template>

<script>
import TermList from './components/TermList'

export default {
  name: 'app',
  components: {
    TermList
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Abril+Fatface|Raleway');

body {
  background-image: url('http://bit.ly/2u3uKZr');
  font-family: 'Raleway', sans-serif;
}

h1, h2 {
  font-family: 'Abril Fatface', serif;
  margin: 0;
}

h1, h4 {
  background-color: rgba(255, 255, 255, 0.95);
  text-align: center;
}

h4 {
  margin: 0;
  padding-bottom: 5px;
}
</style>
