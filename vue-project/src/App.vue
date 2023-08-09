<script setup>
// alert("HOla desde js")
const name = 'vue dinámico'
const styleColor = "color:blue"
</script>

<template>
<h1>Hola {{ name }}</h1>

<h2 v-bind:style="styleColor">Soy AZUL</h2>
</template>

<style scoped>
h1{
  color:red;
}
</style>
