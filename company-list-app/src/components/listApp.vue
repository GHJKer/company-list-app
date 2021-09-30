<template>
  <div class="wrapper">
    <div>
        <div class="add-btn-container"><addCompany /></div>
        <div class="add-group">
        <textarea></textarea>
        <textarea></textarea>
        <textarea></textarea>
        <textarea></textarea>
        <textarea></textarea>
        </div>
    </div>
    <div class="companies-container">
      <div class="name-header font-weight"><strong>Имя:</strong></div>
      <div class="font-weight">Адрес:</div>
      <div class="font-weight">ОГРН(13):</div>
      <div class="font-weight">ИНН(10):</div>
      <div class="font-weight">Дата регистрации:</div>
    </div>
    <hr>
    <ul>
      
      <li
        v-for="(company, index) in companies"
        :key="index"
      >
        <appItem 
          :company="company"
          @remove-company="removeCompany"
        />
        <hr>
      </li>
    </ul>
  </div>
</template>

<script>
import appItem from "./appItem.vue";
import addCompany from './addCompany.vue'

export default {
  components: {
    appItem, addCompany
  },
  data() {
    return {
      companies: [
        {
          id: 1,
          name: "OOO GasOilNorthCompanyKJHFKHAKLDJAHKAD",
          address: "г.Тюмень, ул.Ленина, д.9, оф.902",
          ogrn: 6486936598634,
          inn: 7462307844,
          date: "29.01.2019",
        },
        {
          id: 2,
          name: "OOO Советский угледобывающий завод",
          address: "г.Ленинград, ул.Пушкина, д.17, ст 4",
          ogrn: 2136932348653,
          inn: 9899676231,
          date: "29.01.2019",
        },
        {
          id: 3,
          name: "OАO РЖД",
          address: "г.Волгоград, ул.Ватутина, д.4, оф.23",
          ogrn: 6486936598634,
          inn: 7462307844,
          date: "29.01.2019",
        }
      ],
    };
  },
  methods: {
    removeCompany(id) {
      this.companies = this.companies.filter(t => t.id !== id)
    }
  }
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Montserrat&display=swap");

.bd {
  border: 1px solid red;
}

.wrapper {
  padding: 10px 2px;
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

.add-btn-container {
  display: flex;
  justify-content: flex-end;
}

.add-group {
  display: flex;
  justify-content: space-between;
  margin-bottom: 10px;
}

ul {
  list-style: none;
  padding: 0px;
}

textarea {
  /* margin-right: 35px; */
  width: 150px;
}

div {
  font-family: "Montserrat", sans-serif;
}
</style>