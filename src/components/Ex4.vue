<script setup>
import { ref } from 'vue'

const items = ref(['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'])
const newItem = ref('')

function deleteItem(index) {
  items.value.splice(index, 1)
}

function addItem(event) {
  items.value.push(newItem.value)
  newItem.value = ''
}
</script>

<template>
  <h2>Shopping Cart</h2>

  <ul>
    <li v-for="(value, index) in items" :key="value">
      {{ value }}
      <button type="button" @click="deleteItem(index)">Delete!</button>
    </li>
  </ul>

    <input v-model="newItem">
    <button @click="addItem" type="submit" @keyup.enter="addItem">Add!</button>
</template>