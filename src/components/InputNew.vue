<script setup>
import { ref, defineEmits } from "vue";

const text = ref("");
const emits = defineEmits(["onNewItem"]);

function handleSubmit() {
    if(text !== ""){
        emits("onNewItem",text);
        text.value = "";
    }
}
</script>

<template>
    <form action="" @submit.prevent="handleSubmit">
        <input type="text" v-model="text" placeholder="Añadir item...">
    </form>
</template>

<style scoped>
form{
    margin-bottom: 10px;
}
input{
    width: 100%;
    border: 1px solid rgb(80, 80, 80);
    background-color: rgb(36, 36, 36);
    color: antiquewhite;
}
</style>