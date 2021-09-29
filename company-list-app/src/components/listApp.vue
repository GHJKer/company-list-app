<template>
  <div class="wrapper bd">
    <div class="companies-container">
      <div class="name-header font-weight"><strong>Имя:</strong></div>
      <div class="font-weight">Адрес:</div>
      <div class="font-weight">ОГРН(13):</div>
      <div class="font-weight">ИНН(10):</div>
      <div class="font-weight">Дата регистрации:</div>
    </div>
    <ul>
      <li
        v-for="(company, index) in companies"
        :key="index"
      >
        <appItem 
          :company="company"
        />
      </li>
    </ul>
  </div>
</template>

<script>
import appItem from "./appItem.vue";

export default {
  components: {
    appItem,
  },
  data() {
    return {
      companies: [
        {
          id: 1,
          name: "OOO GasOilNorthCompanyKJHFKHAKLDJAHKAD",
          address: "Тюмень, ул.Ленина, д.9, оф.902",
          ogrn: 6486936598634,
          inn: 7462307844,
          date: "29.01.2019",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Montserrat&display=swap");

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

.name-header {
  margin-right: 60px;
}

.font-weight {
  font-weight: bold;
}

ul {
  list-style: none;
  padding: 0px;
}

li {
  border: 1px solid red;
}

div {
  font-family: "Montserrat", sans-serif;
}
</style>