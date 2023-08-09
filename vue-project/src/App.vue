<script setup>
const name = 'vue dinámico';

// Métodos
const handleClick = () => {
  console.log("Me diste click");
};

const arrayFrutas = ['🍏', '🍇', '🍓', '🥝', '🍒'];
</script>

<template>
  <h1>Hola {{ name.toLocaleUpperCase() }}</h1>
  <button v-on:click="handleClick">Activame 1</button>
  <button @click="handleClick">Activame 2</button>
</template>

<style scoped>
h1 {
  color: red;
}
</style>
