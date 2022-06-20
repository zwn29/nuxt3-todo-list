<template>
  <div
    class="text-pink-500 text-center border mx-1 mt-10 rounded py-2 flex justify-evenly "
  >
    <div class="">
      {{ text }}
    </div>
    <div class="text-lg  ">
      <span
        @click="buttonClick"
        class="cursor-pointer px-2  rounded m-1 border"
      >
        -
      </span>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(['text'])
const emit = defineEmits(['deleteItem'])

const buttonClick = () => {
  emit('deleteItem')
}
</script>

<style></style>
