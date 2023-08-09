<template>
  <div class="container">
    <h1>Hola {{ name.toLocaleUpperCase() }}</h1>
    <!-- Botón para incrementar el contador -->
    <button @click="incrementCounter">Incrementar</button>
    <!-- Mostrar el valor del contador con color condicional -->
    <h2 :class="getCounterClass()">
      Contador: {{ counter }}
    </h2>
    <!-- Botón para decrementar el contador -->
    <button @click="decrementCounter">Decrementar</button>
    <!-- Botón para resetear el contador -->
    <button @click="resetCounter">Resetear</button>
    <!-- Botón para añadir al array -->
    <button @click="addToNumberArray" :disabled="isInNumberArray">
      Añadir {{ counter }} al array
    </button>
    <!-- Botón para mostrar números guardados -->
    <button @click="showNumberArray">Mostrar Números Guardados</button>
    <!-- Botón para ocultar números guardados -->
    <button @click="hideNumberArray" :disabled="!showNumbers">Ocultar Números Guardados</button>
    <!-- Botón para guardar números en otro array -->
    <input v-model="numberToAdd" type="number" placeholder="Número a añadir" />
    <button @click="saveNumber">Guardar Número</button>
    <!-- Botón para mostrar u ocultar números guardados en otro array -->
    <button @click="toggleSavedNumbers">
      {{ showSavedNumbers ? 'Ocultar' : 'Mostrar' }} Números Guardados
    </button>
    <!-- Mostrar números guardados en pantalla -->
    <p v-if="showNumbers">Números Guardados: {{ numberArray.join(', ') }}</p>
    <!-- Mostrar números guardados en otro array en pantalla -->
    <p v-if="showSavedNumbers">Números Guardados en Otro Array: {{ savedNumbers.join(', ') }}</p>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';

const name = 'vue dinámico';

// Crear una variable reactiva para el contador
const counter = ref(0);

// Crear un array para almacenar los números añadidos
const numberArray = ref([]);

// Crear un array para almacenar los números guardados en otro array
const savedNumbers = ref([]);

// Controlar si se muestran los números guardados
const showNumbers = ref(false);
const showSavedNumbers = ref(false);

// Número para agregar al array
const numberToAdd = ref('');

// Función para incrementar el contador
const incrementCounter = () => {
  counter.value++;
};

// Función para decrementar el contador
const decrementCounter = () => {
  counter.value--;
};

// Función para obtener la clase del contador
const getCounterClass = () => {
  if (counter.value === 0) {
    return 'cero';
  } else if (counter.value > 0) {
    return 'positivo';
  } else {
    return 'negativo';
  }
};

// Función para resetear el contador
const resetCounter = () => {
  counter.value = 0;
};

// Función para agregar al array y verificar si el número ya está en el array
const addToNumberArray = () => {
  if (!numberArray.value.includes(counter.value)) {
    numberArray.value.push(counter.value);
  }
};

// Comprobar si el número actual ya está en el array
const isInNumberArray = computed(() => numberArray.value.includes(counter.value));

// Función para mostrar números guardados
const showNumberArray = () => {
  showNumbers.value = true;
};

// Función para ocultar números guardados
const hideNumberArray = () => {
  showNumbers.value = false;
};

// Función para guardar un número en el otro array
const saveNumber = () => {
  if (numberToAdd.value !== '') {
    savedNumbers.value.push(Number(numberToAdd.value));
    numberToAdd.value = '';
  }
};

// Función para mostrar u ocultar números guardados en otro array
const toggleSavedNumbers = () => {
  showSavedNumbers.value = !showSavedNumbers.value;
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

input {
  padding: 5px;
  font-size: 14px;
  margin-right: 5px;
}

.positivo {
  color: green;
}

.negativo {
  color: red;
}

.cero {
  color: white;
}
</style>
