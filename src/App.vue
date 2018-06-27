<template>
  <div id="app">
    <Navigation></Navigation>
    <Editions></Editions>
    <Users></Users>
    <Years></Years>
    <Support></Support>
    <Summary></Summary>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Navigation from './components/Navigation.vue'
import Editions from './components/Editions.vue'
import Users from './components/Users.vue'
import Years from './components/Years.vue'
import Support from './components/Support.vue'
import Summary from './components/Summary.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Navigation,
    Editions,
    Users,
    Years,
    Support,
    Summary,
  }
}
</script>

<style>

body {
  margin: 0;
  padding: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-family: 'Scada', sans-serif;
}
</style>
