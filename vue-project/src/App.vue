<template>
  <div class="container">
    <h1>Hola {{ name.toLocaleUpperCase() }}</h1>
    <!-- Botón para incrementar el contador -->
    <button @click="incrementCounter">Incrementar</button>
    <!-- Mostrar el valor del contador -->
    <p>Contador: {{ counter }}</p>
    <!-- Botón para decrementar el contador -->
    <button @click="decrementCounter">Decrementar</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const name = 'vue dinámico';

// Crear una variable reactiva para el contador
const counter = ref(0);

// Función para incrementar el contador
const incrementCounter = () => {
  counter.value++;
};

// Función para decrementar el contador
const decrementCounter = () => {
  counter.value--;
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 20px;
  text-align: center;
}

h1 {
  color: red;
  font-size: 24px;
  margin-bottom: 10px;
}

button {
  margin: 5px;
  padding: 10px 20px;
  font-size: 16px;
}
</style>
