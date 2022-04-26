<script setup>
  import SortableTable from './components/SortableTable.vue'
</script>

<template>
  <main>
    <h1>Sortable table</h1>
    <SortableTable />
  </main>
</template>

<style>
  body {
    margin: 0;
    padding: 0;
    background-color: hsla(0, 100%, 50%, 1);
    background-image: radial-gradient(
        at 40% 20%,
        hsla(28, 100%, 74%, 1) 0px,
        transparent 50%
      ),
      radial-gradient(at 80% 0%, hsla(189, 100%, 56%, 1) 0px, transparent 50%),
      radial-gradient(at 0% 50%, hsla(355, 100%, 93%, 1) 0px, transparent 50%),
      radial-gradient(at 80% 50%, hsla(340, 100%, 76%, 1) 0px, transparent 50%),
      radial-gradient(at 0% 100%, hsla(22, 100%, 77%, 1) 0px, transparent 50%),
      radial-gradient(at 80% 100%, hsla(242, 100%, 70%, 1) 0px, transparent 50%),
      radial-gradient(at 0% 0%, hsla(343, 100%, 76%, 1) 0px, transparent 50%);
  }
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }
  main {
    min-height: 100vh;
  }
  h1 {
    margin: 0;
    padding: 1em;
  }
</style>
