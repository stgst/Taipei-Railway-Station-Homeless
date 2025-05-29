<script setup>
import { inject } from 'vue'

const pageID = inject('pageID')

const handleClickPLUS = () => {
  pageID.value++
}
const handleClickSUB = () => {
  pageID.value--
  if (pageID.value < 0) {
    pageID.value = 0 // 確保不會小於0
  }
}

</script>

<template>
  <div id="btn" class="flex items-center justify-center">
    <button class="cursor-pointer mx-5 animate__animated animate__pulse animate__infinite" @click="handleClickSUB">
      <img src="@/assets/img/btn.png" class=" w-15 h-15 md:w-12 md:h-12 border-2 border-white rounded-full rotate-90">
    </button>
    <button class="cursor-pointer mx-5 animate__animated animate__pulse animate__infinite" @click="handleClickPLUS">
      <img src="@/assets/img/btn.png" class=" w-15 h-15 md:w-12 md:h-12 border-2 border-white rounded-full rotate-270">
    </button>
  </div>
</template>