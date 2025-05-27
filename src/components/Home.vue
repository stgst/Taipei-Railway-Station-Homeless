<script setup>
import Btn from '@/components/Btn.vue'
</script>

<template>

    <div id="title" class="leading-15 text-white">
        <div class="text-left animate__animated animate__fadeInDown">
            <span class="text-5xl ml-10 ">你聽過</span><br>
        </div>
        <div class="text-right animate__animated animate__fadeIn">
            <span class="text-7xl text-center me-15 text-violet-200">無家者</span><br>
        </div>
        <div class="text-right animate__animated animate__fadeInUp">
            <span class="text-5xl mr-10">嗎？</span>
        </div>
    </div>
    <div id="icon" class="animate__animated animate__bounceIn text-left mt-10">
        <img src="@/assets/img/icon_airplane.png">
        
    </div>
    <div class="absolute bottom-20 left-0 right-0">
        <Btn />
    </div>

</template>

<style>
#title {
    font-family: 'Noto Serif TC', sans-serif;
    font-weight: 900;
    position: relative;
}

* {
    z-index: 10;
}

#icon {
    position: absolute;
    top: 50%;
}
</style>