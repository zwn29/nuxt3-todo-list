<template>
  <div
    class=" text-lg   text-pink-500 text-center border mx-1 mt-10 rounded py-2 "
  >
    Todo List
  </div>
  <form @submit.prevent>
    <input
      @keyup.enter="addTodo"
      type="text"
      v-model="newTodo"
      placeholder="hello"
      class="border box text-pink-200 focus:ring-transparent active:ring-transparent py-2 rounded block mx-1 mt-5 w-[98.8%] focus:outline-none "
    />
  </form>

  <div v-for="a in arr">
    <Todo :text="a" @delete-item="delItem" />
  </div>
</template>

<script setup>
const arr = ref([])
const newTodo = ref('')

const addTodo = e => {
  if (newTodo.value !== '') {
    arr.value.push(newTodo.value)
    newTodo.value = ''
    console.log(arr.value)
  }
}

const delItem = a => {
  console.log(a)
  arr.value.splice(a, 1)
}
</script>

<style>
body {
  background-color: #000;
}

.box {
  border: 1px solid #ffe6e6 !important;
}

.box:focus {
  border: 1px solid #f6c6ea !important;
}
</style>
