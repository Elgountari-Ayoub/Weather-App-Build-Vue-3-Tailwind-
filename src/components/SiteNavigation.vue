<template>
    <header class="stiky top-0 bg-weather-primary shadow-lg">
        <nav class="container flex flex-col sm:flex-row items-center gap-4 text-white py-6">
            <RouterLink :to = "{name : 'home'}">
                <div class="flex items-center gap-3">
                    <i class="fa-solid fa-sun text2x"></i>
                    <p class="text-2xl">The Local Weather</p>
                </div>
            </RouterLink>
            <div class="flex gap-3 flex-1 justify-end">
                <i class="fa-solid fa-circle-info text-xl cursor-pointer hover:text-weather-secondary duration-150"></i>
                <i class="fa-solid fa-plus text-xl cursor-pointer hover:text-weather-secondary duration-150"></i>
            </div>
        </nav>
    </header>
</template>

<script setup>
import { RouterLink } from 'vue-router';
</script>
