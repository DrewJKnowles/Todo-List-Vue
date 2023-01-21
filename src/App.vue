<script setup lang="ts">
import { ref, onMounted, computed, watch } from 'vue';

const todos = ref([])
const name = ref('')

const input_content = ref('')
const input_category = ref(null)


// const todo_src = computed(() => todos.value.sort((a, b) => {
//   return a.createdAt - b.createdAt
// }))

watch(name, (newVal) => {
  localStorage.setItem('name', newVal)
})

const addTODO = () => {};
 
onMounted(() => {
  name.value = localStorage.getItem('name') || ''
})
</script>
 

<template>
  <main class="app">
    <section class="greeting">
      <h2 class="'title'">
        What's up, <input type="text" placeholder="Name here"
        v-model="name">
      </h2>
    </section>

    <section class="create-todo">
      <h3>CREATE TODO</h3>

      <form @submit.prevent="addTODO"></form>
    </section>
  </main>
</template>
