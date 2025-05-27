<template>

    <div id="title" class="leading-15 text-white">
        <div class="text-left">
            <span class="text-5xl ml-10"></span><br>
        </div>
        <div class="text-right">
            <span class="text-7xl text-center me-15 text-violet-200">無家者</span><br>

            <div class="text-right"></div>
            <span class="text-5xl mr-10">嗎？</span>
        </div>
    </div>
    <div id="icon" class="text-left mt-10">
        <img src="@/assets/img/icon_airplane.png">
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