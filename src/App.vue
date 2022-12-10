<template>
  <h1>Chart Example</h1>
  <section>
    <ChartVue />
    <DecisionsVue />
  </section>
</template>

<script>
import ChartVue from './components/Chart.vue';
import DecisionsVue from './components/Decisions.vue';
export default {
  name: 'App',
  components: {
    ChartVue,
    DecisionsVue,
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
  padding: 0 15%;
  height: 100vh;
  /* background-color: aqua; */
}
h1 {
  /* height: 10%; */
}
section {
  display: flex;
  align-items: center;
  justify-content: center;
  /* background-color: green; */
  /* height: 88%; */
}
</style>
