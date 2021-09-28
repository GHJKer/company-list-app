<template>
    <div class="fields">
      <div class="name db"></div>
      <div class="address db"></div>
      <div class="ogrn db"></div>
      <div class="inn db"></div>
      <div class="date db"></div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            companyInfo: [
                {id: 1,  name: 'OOO GasOilNorthCompany', address: 'Тюмень, ул.Ленина, д.9, оф.902', orgn: 6486936598634, inn: 7462307844, date: '29.01.2019'}
            ]
        }
    }
}
</script>

<style lang="scss" scoped>

.fields {
    display: flex;
    justify-content: space-between;
}

.db {
    border: 1px solid rgb(6, 151, 6);
}

/* .name {
    width: 100px;
}

.address {
    width: 100px;
}

.ogrn {
    width: 100px;
}

.inn {
    width: 100px;
}

.data {
    width: 100px;
} */
</style>