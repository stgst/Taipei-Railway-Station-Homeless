<script setup>
import { inject } from 'vue'

const pageID = inject('pageID')

const handleClick = () => {
  pageID.value++
}
</script>

<template>
  <div id="btn" class="flex items-center justify-center">
    <button 
      class="cursor-pointer animate__animated animate__pulse animate__infinite"
      @click="handleClick"
    >
      <img src="@/assets/img/btn.png" class=" w-15 h-15 md:w-12 md:h-12 border-2 border-white rounded-full">
    </button>
  </div>
</template>