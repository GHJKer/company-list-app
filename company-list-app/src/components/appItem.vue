<template>
    <div class="fields">
      <div class="name">{{ company.id }}) {{ company.name }}</div>
      <div class="address">{{ company.address }}</div>
      <div class="ogrn">{{ company.ogrn }}</div>
      <div class="inn">{{ company.inn }}</div>
      <div class="date">{{ company.date }}</div>
      <div><button type="button" class="close-btn" v-on:click="$emit('remove-company', company.id)">&times;</button></div>
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
}

.close-btn {
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

.close-btn:active {
  transform: translateY(1px);
  filter: saturate(150%);
  border: 3px solid #70808d;
}

.close-btn:hover {
  color: #bfbbc0;
  /* border-color: currentColor; */
  background-color: #4e5a64;
}
</style>