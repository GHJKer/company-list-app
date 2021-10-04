<template>
    <div class="fields">
      <div class="name">{{ index + 1 }}) {{ company.name }}</div>
      <div class="address" v-if="!toEdit" v-on:click="toEdit = !toEdit">{{ company.address }}</div>
      <div v-if="toEdit">
          <textarea v-model="company.address">
          </textarea>
          <button class="btn-styles" @click="(addressField = company.address), (toEdit = false)">Сохранить</button>
      </div>
      <div class="ogrn">{{ company.ogrn }}</div>
      <div class="inn">{{ company.inn }}</div>
      <div class="date">{{ company.date }}</div>
      <div><button type="button" class="btn-styles" v-on:click="$emit('remove-company', company.id)">&times;</button></div>
    </div>
</template>

<script>
export default {
    props: {
        company: {
            type: Object,
            required: true
        },
        index: Number
    },
    data() {
        return {
            toEdit: false,
            addressField: ""
        }
    }
}
</script>

<style lang="scss" scoped>

.fields {
    display: flex;
    justify-content: space-between;
}

.name {
    width: 180px;
    margin-right: 20px;
    word-break: break-word;
    padding: 5px;
}

.address {
    width: 110px;
    margin-right: 55px;
    padding: 5px;
    word-break: break-word;
    border: 3px solid transparent;
    border-radius: 4px;
}

.address:hover {
    border: 3px solid #70808d;
    border-radius: 4px;
}

.ogrn {
    width: 135px;
    margin-right: 73px;
    padding: 5px;
}

.inn {
    width: 110px;
    margin-right: 100px;
    padding: 5px;
}

.date {
    width: 100px;
    padding: 5px;
    margin-right: 20px;
    word-break: break-word;
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
    background-color: #6C757D;
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
</style>