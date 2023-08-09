<script setup>
const name = 'vue dinámico';

// Métodos
const handleClick = (message) => {
  console.log(message);
};

const arrayFrutas = ['🍏', '🍇', '🍓', '🥝', '🍒'];
</script>

<template>
  <h1>Hola {{ name.toLocaleUpperCase() }}</h1>
  <button v-on:click="handleClick('Texto1')">Activame 1</button>
  <button @click="handleClick('Texto2')">Activame 2</button>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

h1 {
  color: red;
}
</style>
<!-- Voy 1h05 del video Fundamentos de Vue 3 con Composition API: Aprende a crear aplicaciones web modernas y escalables

Bluuweb -->