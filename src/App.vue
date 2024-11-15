<template>
  <ItemForm :editingItem="editingItem" @addOrUpdate="addOrUpdate"/>
  <ListItems :items="items" @editItem="handleEdit" @deleteItem="handleDelete"/>
</template>

<script setup>
import { ref } from 'vue'
import ItemForm from './components/ItemForm.vue';
import ListItems from './components/ListItems.vue';

const items = ref([
    { id: 1, name: 'Apple', description: 'A red apple'},
    { id: 2, name: 'Banana', description: 'A yellow banana'},
    { id: 3, name: 'Cherry', description: 'A red cherry'},
    { id: 4, name: 'Grape', description: 'A purple grape'},
    { id: 5, name: 'Kiwi', description: 'A brown kiwi'},
    { id: 6, name: 'Orange', description: 'An orange orange'},
    { id: 7, name: 'Peach', description: 'A pink peach'},
    { id: 8, name: 'Pear', description: 'A green pear'},
    { id: 9, name: 'Pineapple', description: 'A yellow pineapple'},
    { id: 10, name: 'Strawberry', description: 'A red strawberry'},
    { id: 11, name: 'Watermelon', description: 'A green watermelon'}
])

const editingItem = ref({ id: null, name: '', description: '' })

function handleDelete(itemId) {
  items.value = items.value.filter(i => i.id !== itemId)
}

function handleEdit(item) {
  editingItem.value = { ...item }
}

function addOrUpdate(item) {
  console.log(item)
  if (item.id) {
    // find item with existing id, if it exists, replace with new data
    const index = items.value.findIndex(i => i.id === item.id)
    if (index !== -1) {
      items.value[index] = { ...item }
    }
  } else {
    // otherwise, create new item by finding next possible id and adding it to items
    item.id = items.value.length ? Math.max(...items.value.map(i => i.id)) + 1 : 1
    items.value.push(item)
  }
  editingItem.value = { id: null, name: '', description: ''}
}

</script>