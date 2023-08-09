<script setup>
// alert("HOla desde js")
const name = 'vue dinámico'
const styleColor = "color:blue"
const arrayColores = ["blue","red","peru"]
const active = true
// const active = false
</script>

<template>
<h1>Hola {{ name.toLocaleUpperCase() }}</h1>

<h2 v-bind:style="styleColor">Soy AZUL</h2>
<!-- Cuando cambia el indice cambia el color -->
<h2 v-bind:style="`color: ${arrayColores[2]}`">Soy Peru </h2>

<h2>
  {{ active ? "Estoy activo" : "Estoy Inactivo" }}
</h2>
<h3>{{ arrayColores }}</h3>
</template>

<style scoped>
h1{
  color:red;
}
</style>
