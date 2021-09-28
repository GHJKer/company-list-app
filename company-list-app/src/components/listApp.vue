<template>
  <div class="wrapper bd">
    <div class="companies-container">
      <div><strong>Имя:</strong></div>
      <div>Адрес:</div>
      <div>ОГРН(13):</div>
      <div>ИНН(10):</div>
      <div>Дата регистрации:</div>
    </div>
    <ul>
      <li><appItem /></li>
    </ul>
  </div>
</template>

<script>
import appItem from "./appItem.vue";

export default {
  components: {
    appItem,
  },
};
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat&display=swap');

.bd {
  border: 1px solid red;
}

.wrapper {
  margin-left: 15px;
  margin-right: 15px;
  padding: 10px 5px;
}

.companies-container {
    display: flex;
    justify-content: space-between;
}

ul {
  list-style: none;
  padding: 0px;
}

li {
  border: 1px solid red;
}

div {
    font-family: 'Montserrat', sans-serif;
}
</style>