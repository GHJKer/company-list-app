<template>
  <div class="wrapper">
    <div class="show-add-btn-container">
      <button 
        class="show-add-btn btn-styles"
        @click="showButtons = true"
      >
        + Добавить
      </button>
    </div>
    <div class="add-btns-container" v-if="showButtons">
        <addCompany 
          @add-company="addCompany"
          @closeModal="showButtons = false"
        />
    </div>
    <div class="companies-container">
      <div class="name-header font-weight"><strong>Имя:</strong></div>
      <div class="font-weight">Адрес:</div>
      <div class="font-weight">ОГРН(13):</div>
      <div class="font-weight">ИНН(10):</div>
      <div class="font-weight">Дата регистрации:</div>
    </div>
    <hr />
    <ul>
      <li v-for="(company, i) in companies" :key="i">
        <appItem :company="company" 
          @remove-company="removeCompany" 
          :index="i"
        />
        <hr />
      </li>
    </ul>
  </div>
</template>

<script>
import appItem from "./appItem.vue";
import addCompany from "./addCompany.vue";

export default {
  components: {
    appItem,
    addCompany,
  },
  data() {
    return {
      showButtons: false,
      companies: [
        
      ],
    };
  },
  methods: {
    removeCompany(id) {
      this.companies = this.companies.filter((t) => t.id !== id);
    },
    addCompany(company) {
      this.companies.push(company)
    }
  },
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Montserrat&display=swap");

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



.show-add-btn-container {
  display: flex;
  justify-content: flex-end;
  margin-bottom: 10px;
}

.btn-styles {
  font: inherit;
  cursor: pointer;

  display: inline-block;
  text-align: center;
  text-decoration: none;
  margin: 2px 0;
  border: solid 3px transparent;
  border-radius: 4px;
  padding: 0.15em 0.3em;
  color: #ffffff;
  background-color: #6c757d;
}

.btn-styles:active {
  transform: translateY(1px);
  filter: saturate(150%);
  border: 3px solid #70808d;
}

.btn-styles:hover {
  color: #bfbbc0;
  background-color: #4e5a64;
}

ul {
  list-style: none;
  padding: 0px;
}


div {
  font-family: "Montserrat", sans-serif;
}
</style>