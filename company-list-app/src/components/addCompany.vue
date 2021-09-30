<template>
    <div class="add-btn-container"><button class="add-btn"><span>Добавить компанию</span></button></div>
</template>

<script>
export default {
    
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap');

.add-btn {
    font: inherit;
    cursor: pointer;

    display: inline-block;
    text-align: center;
    text-decoration: none;
    margin: 2px 0;
    border: solid 4px transparent;
    border-radius: 4px;
    padding: 0.15em 0.3em;
    color: #ffffff;
    background-color: #6C757D;
}

.add-btn:active {
  transform: translateY(1px);
  filter: saturate(150%);
  border: 4px solid #6b7a88;
}

.add-btn:hover {
  color: #bfbbc0;
  background-color: #4e5a64;
}

.add-btn-container {
    margin-bottom: 10px;
}

span {
    font-family: "Montserrat", sans-serif;
}

</style>