<template>
    <form class="item-form" @submit.prevent="">
        <label>Item name:</label>
        <input type="text" placeholder="Enter item name" v-model="localItem.name">

        <label>Item description:</label>
        <input type="text" placeholder="Enter item description" v-model="localItem.description">

        <button type="submit" @click="addOrUpdate(localItem)">{{ localItem.id ? 'Update' : 'Create' }}</button>
    </form>
</template>

<script setup>
import { ref, watch } from 'vue'

const props = defineProps(['editingItem'])
const emit = defineEmits(['addOrUpdate'])

// init local item to input prop
const localItem = ref({ ...props.editingItem })

// watch changes to prop and reflect in local item
watch(() => props.editingItem, (newVal) => localItem.value = { ...newVal })

// emit addOrUpdate so App.vue knows what to do with item
function addOrUpdate(item) {
    emit('addOrUpdate', item)
    localItem.value = { id: null, name: '', description: '' }
}

</script>

<style>
    .item-form {
        text-align: center;
        margin-bottom: 50px;
    }
</style>