<script setup>
import { defineProps } from 'vue';
const props = defineProps(
    {
        texto : {
            type : String
        },
        tipo : {
            type : String,
            default : "padrao"
        }
        
    }
)
</script>

<template>
    <p :class = "tipo">
        {{ texto }}
    </p>
</template>

<style scoped>
.padrao{
    background-color: rgb(177, 176, 176);
    padding: 10px;
    border-radius: 10px;
}
.sucesso{
    background-color: rgb(124, 242, 21);
    padding: 10px;
    border-radius: 10px;
}
.falha{
    background-color: rgb(245, 27, 27);
    padding: 10px;
    border-radius: 10px;
}

</style>