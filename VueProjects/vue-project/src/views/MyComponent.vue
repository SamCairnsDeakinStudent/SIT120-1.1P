
<script setup>
import { ref } from 'vue';

const message= ref("Hello! This message if from a component!")

const changeMessage = () => {
    message.value = 'Updated Message!';
};
</script>

<template>
    <div>
        <h2> {{ message }}</h2>
        <button @click="changeMessage"> Change Message! </button>
    </div>
</template>