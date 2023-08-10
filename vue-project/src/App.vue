<template>
<div>
  <h1>Padre:</h1>
  <HijoVue :nombre="nombre" :edad="edad" @modificar="cambiarValor"/>
</div>

</template>

<script setup>
import { ref } from "vue";
import HijoVue from "./components/Hijo.vue";

const cambiarValor =(valor1,valor2)=>{
  nombre.value=valor1;
  edad.value=valor2;
}
const nombre = ref('Jab');
const edad=ref(18);
</script>

<style scoped>

</style>
