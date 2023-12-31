<script setup>
import { defineProps } from 'vue';
const props = defineProps(["titulo" , "conteudo"])
</script>

<template>
    <div class = "card-container">
        <h4>{{titulo}}</h4>
        <p>{{conteudo}}</p>
    </div>

</template>

<style scoped>

.card-container{
    background-color: rgb(252, 252, 126);
    border: 1px solid black;
    border-radius: 10px;
    padding: 5px;
    margin: 10px;
}

</style>