<script setup>
import { ref } from "vue";

const todoItems = ref(["Walk the dog", "Wash the cat", "Talk to the hand"]);
const newItem = ref("");

const addNewItem = () => {
  todoItems.value.push(newItem.value);
  newItem.value = "";
};

const deleteItem = (i) => {
  todoItems.value.splice(i, 1);
};
</script>

<template>
  <ul>
    <div v-for="(todoItem, i) in todoItems">
      <li>{{ todoItem }}</li>
      <button @click="deleteItem(i)">delete</button>
    </div>
  </ul>
  <input type="text" v-model="newItem" v-on:keyup.enter="addNewItem" />
</template>

<style scoped></style>
