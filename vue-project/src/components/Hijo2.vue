<template>
    <div>
        <h1>Hijo2:</h1>
        <h2> {{ canal }}</h2>
        
    </div>
</template>

<script setup>
import { inject } from 'vue';


const canal=inject('miCanal')
</script>

<style scoped></style>
