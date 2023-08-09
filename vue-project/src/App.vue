<script setup>
const name = 'vue dinámico';

// Métodos
const handleClick = (message) => {
  console.log(message);
};

const arrayFrutas = ['🍏', '🍇', '🍓', '🥝', '🍒'];
</script>

<template>
  <div class="container">
    <h1>Hola {{ name.toLocaleUpperCase() }}</h1>
    <!-- Clics del raton -->
    <button v-on:click.right.prevent="handleClick('Texto Right')">Activame right</button>
    <button v-on:click="handleClick('Texto Left')">Activame left</button>
    <button @click.middle="handleClick('Texto Middle')">Activame middle</button>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 20px;
  /* Añadido para un espacio alrededor de los elementos */
  text-align: center;
  /* Centrar el texto en dispositivos móviles */
}

h1 {
  color: red;
  font-size: 24px;
  /* Tamaño de fuente más pequeño para dispositivos móviles */
  margin-bottom: 10px;
  /* Espaciado inferior */
}

button {
  margin: 5px;
  padding: 10px 20px;
  font-size: 16px;
  /* Tamaño de fuente más grande para botones en móviles */
}</style>

<!-- Voy 1h05 del video Fundamentos de Vue 3 con Composition API: Aprende a crear aplicaciones web modernas y escalables

Bluuweb -->