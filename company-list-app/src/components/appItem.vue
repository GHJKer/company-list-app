<template>
    <div class="fields">
      <div class="name db">{{ company.name }}</div>
      <div class="address db">{{ company.address }}</div>
      <div class="ogrn db">{{ company.ogrn }}</div>
      <div class="inn db">{{ company.inn }}</div>
      <div class="date db">{{ company.date }}</div>
    </div>
</template>

<script>
export default {
    props: {
        company: {
            type: Object,
            required: true
        }
    }
}
</script>

<style lang="scss" scoped>

.fields {
    display: flex;
    /* justify-content: space-between; */
}

.db {
    border: 1px solid rgb(6, 151, 6);
}

.name {
    width: 180px;
    margin-right: 20px;
    word-break: break-all;
    padding: 5px;
}

.address {
    width: 110px;
    margin-right: 55px;
    padding: 5px;
}

.ogrn {
    width: 135px;
    margin-right: 73px;
    padding: 5px;
}

.inn {
    width: 110px;
    margin-right: 150px;
    padding: 5px;
}

.date {
    width: 100px;
    padding: 5px;
}
</style>