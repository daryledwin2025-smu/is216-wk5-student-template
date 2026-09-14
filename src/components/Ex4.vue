<script setup>
import { ref } from 'vue'
const items = ref(['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'])
function deleteItem(index) {
  items.value.pop(index);
}
</script>

<template>
  <h2>Shopping Cart</h2>
   <form action="">
    <ul>
      <div v-for="(value, index) in items" :key="value">
    <li>{{ value }}</li>
    <button type="button" @click="deleteItem(index)">Delete</button>
      </div>

    </ul>
   </form>
   <div v-for="value in items">
    {{ value }}
   </div>
</template>
