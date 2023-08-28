<script setup>
import { ref } from 'vue';

const itemID = ref(0);
const item = ref(' ');
const itemlist = ref([]);
const check = ref(false);

function addItem() {
    itemlist.value.push({
        id: itemID.value++,
        newItem: item.value,
        status: check.value
    })

}

function removeitem(itemtoremove){
    itemlist.value = itemlist.value.filter(xx => xx.id !== itemtoremove.id)
}
</script>

<template>
    <div>
        <h1>This is a Demo Page</h1>
        <input type="text" v-model="item">
        <button @click=addItem> Add! </button>
        <ol>
            <li v-for="i in itemlist" :key="i.id">
            {{ i.newItem }}
            <button @click= "removeitem(i)"> Clear </button>
            </li>
        </ol>
    </div>
</template>


    <style scoped>

    </style>
