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
</style>
