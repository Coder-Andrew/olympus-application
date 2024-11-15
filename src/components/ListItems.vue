<template>
    <div class="items">
        <div class="item" v-for="item in items" :key="item.id">
            <h2>{{ item.name }}</h2>
            <p>{{ item.description }}</p>
            <button @click="handleEdit(item)">Edit</button>
            <button @click="handleDelete(item.id)">Delete</button>
        </div>
    </div>
</template>

<script setup>
const props = defineProps(['items'])
const emit = defineEmits(['editItem', 'deleteItem'])

function handleEdit(item) {
    emit('editItem', item)
}

function handleDelete(itemId) {
    emit('deleteItem', itemId)
}

</script>

<style>
    .items {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        gap: 20px;
    }
    .items .item {
        border: 2px solid darkgrey;
        text-align: center;
        padding: 10px;
        max-width: 20%;
        border-radius: 20px;
        box-sizing: border-box;
        flex-grow: 1;
        background-color: lightgrey;
    }
</style>