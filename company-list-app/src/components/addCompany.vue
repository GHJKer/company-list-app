<template>
  <div class="add-btn-container">
    <div class="add-btns-container">
      <button @click="addCompany" class="add-btn btn-styles">
        <span>Добавить компанию</span>
      </button>
      <button class="close-modal btn-styles" @click="closeModal">
        Закрыть
      </button>
    </div>

    <div class="add-group">
      <div>
        <textarea v-model="name"></textarea>
        <p class="validation" v-if="!$v.name.required">Введите название компании</p>
      </div>
      <div>
        <textarea v-model="address"></textarea>
        <p class="validation" v-if="!$v.address.required">Введите адрес компании</p>
      </div>
      <div>
        <textarea v-model="ogrn"></textarea>
        <p class="validation" v-if="!$v.ogrn.minLength">Не менее 13 цифр!</p>
        <p class="validation" v-if="!$v.ogrn.maxLength">Не более 13 цифр!</p>
        <p class="validation" v-if="!$v.ogrn.required">Введите ОГРН компании</p>
      </div>
      <div>
        <textarea v-model="inn"></textarea>
        <p class="validation" v-if="!$v.inn.minLength">Не менее 10 цифр!</p>
        <p class="validation" v-if="!$v.inn.maxLength">Не более 10 цифр!</p>
        <p class="validation" v-if="!$v.inn.required">Введите ИНН компании</p>
      </div>
      <div>
        <textarea v-model="date"></textarea>
        <p class="validation" v-if="!$v.date.required">Введите дату создания компании</p>
      </div>
      
      
      
      
      
    </div>
  </div>
</template>

<script>
import { validationMixin } from 'vuelidate'
import { minLength, maxLength, required } from 'vuelidate/lib/validators'


export default {
  mixins: [validationMixin],
  data() {
    return {
      name: "",
      address: "",
      ogrn: "",
      inn: "",
      date: ""
    };
  },
  validations: {
    name: {
      required
    },
    address: {
      required
    },
    ogrn: {
      minLength: minLength(13),
      maxLength: maxLength(13),
      required
    },
    inn: {
      minLength: minLength(10),
      maxLength: maxLength(10),
      required
    },
    date: {
      required
    }
  },
  methods: {
    addCompany() {
      if (this.name.trim()) {
        const newCompany = {
          id: Date.now(),
          name: this.name,
          address: this.address,
          ogrn: this.ogrn,
          inn: this.inn,
          date: this.date
        };
        this.$emit("add-company", newCompany);
        this.name = "";
        this.address = "";
        this.ogrn = "";
        this.inn = "";
        this.date = "";
      }
    },
    closeModal() {
      this.$emit("closeModal");
    },
  },
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap");

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

.add-group {
  display: flex;
  justify-content: space-between;
  margin-bottom: 10px;
}

.close-modal {
  margin-left: 10px;
}

.add-btns-container {
  display: flex;
  justify-content: flex-end;
  padding-bottom: 10px;
}

.validation {
  font-size: 10px;
  margin-block-start: 0;
  color: red;
}

textarea {
  width: 150px;
}

span {
  font-family: "Montserrat", sans-serif;
}
</style>