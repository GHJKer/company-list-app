<template>
  <div class="main-container">
    <h1>my company list</h1>
    <listApp />
  </div>
</template>

<script>
import listApp from './components/listApp.vue'

export default {
  name: 'App',
  components: {
    listApp
  }
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap');

.main-container {
  width: 1000px;
  margin-left: auto;
  margin-right: auto;
  background-color: #D8DEF6;
  border-radius: 10px;
  padding-bottom: 10px;
}

h1 {
  text-align: center;
  font-family: 'Bebas Neue', cursive;
}
</style>