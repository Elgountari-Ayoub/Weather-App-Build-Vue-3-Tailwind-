<template>
    <header class="top-0 shadow-lg stiky bg-weather-primary">
        <nav class="container flex flex-col items-center gap-4 py-6 text-white sm:flex-row">
            <RouterLink :to="{ name: 'home' }">
                <div class="flex items-center gap-3">
                    <i class="fa-solid fa-sun text2x"></i>
                    <p class="text-2xl">The Local Weather</p>
                </div>
            </RouterLink>
            <div class="flex justify-end flex-1 gap-3">
                <i class="text-xl duration-150 cursor-pointer fa-solid fa-circle-info hover:text-weather-secondary" @click="toggleModal"></i>
                <i class="text-xl duration-150 cursor-pointer fa-solid fa-plus hover:text-weather-secondary"></i>
            </div>
        </nav>
    </header>

    <BaseModal :modalActive="modalActive" @close-modal="toggleModal">
        <div class="text-black">
            <h1 class="mb-1 text-2xl">About:</h1>
            <p class="mb-4">
                The Local Weather allows you to track the current and
                future weather of cities of your choosing.
            </p>
            <h2 class="text-2xl">How it works:</h2>
            <ol class="mb-4 list-decimal list-inside">
                <li>
                    Search for your city by entering the name into the
                    search bar.
                </li>
                <li>
                    Select a city within the results, this will take
                    you to the current weather for your selection.
                </li>
                <li>
                    Track the city by clicking on the "+" icon in the
                    top right. This will save the city to view at a
                    later time on the home page.
                </li>
            </ol>

            <h2 class="text-2xl">Removing a city</h2>
            <p>
                If you no longer wish to track a city, simply select
                the city within the home page. At the bottom of the
                page, there will be am option to delete the city.
            </p>
        </div>
    </BaseModal>
</template>

<script setup>
import { RouterLink } from 'vue-router';
import BaseModal from './BaseModal.vue';
import { ref } from 'vue';

const modalActive = ref(null);
const toggleModal = ()=> {
    modalActive.value = !modalActive.value;
};
</script>

<!-- <template>
    <div class="container mx-auto">
        <h1 class="mb-8 text-4xl font-bold text-gray-800">My Calendar</h1>

        <div class="flex items-center justify-between mb-4">
            <button class="p-2 bg-gray-200 rounded-full hover:bg-gray-300" @click="previousMonth">
                <i class="fas fa-chevron-left"></i>
            </button>

            <h2 class="text-2xl font-bold text-gray-800">{{ month }}</h2>

            <button class="p-2 bg-gray-200 rounded-full hover:bg-gray-300" @click="nextMonth">
                <i class="fas fa-chevron-right"></i>
            </button>
        </div>

        <div class="grid grid-cols-7 gap-4">
            <div v-for="(day, index) in days" :key="index" class="font-bold text-center text-gray-800 uppercase">
                {{ day }}
            </div>
        </div>

        <div class="grid grid-cols-7 gap-4">
            <div v-for="(day, index) in daysInMonth" :key="index" :class="{
                'text-gray-400': isNotCurrentMonth(day),
                'bg-gray-200': isSelected(day),
            }" @click="selectDate(day)">
                {{ day }}
            </div>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'App',

    data() {
        return {
            selectedDate: null,
            currentDate: new Date(),
        };
    },

    computed: {
        month() {
            return this.currentDate.toLocaleDateString('default', {
                month: 'long',
                year: 'numeric',
            });
        },

        daysInMonth() {
            const year = this.currentDate.getFullYear();
            const month = this.currentDate.getMonth();
            const daysInMonth = new Date(year, month + 1, 0).getDate();
            return Array.from({ length: daysInMonth }, (_, i) => i)
        },

        days() {
            return ['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'];
        },
    },

    methods: {
        previousMonth() {
            this.currentDate.setMonth(this.currentDate.getMonth() - 1);
        },
        nextMonth() {
            this.currentDate.setMonth(this.currentDate.getMonth() + 1);
        },

        isNotCurrentMonth(day) {
            const year = this.currentDate.getFullYear();
            const month = this.currentDate.getMonth();
            const date = new Date(year, month, day);

            return date.getMonth() !== month;
        },

        isSelected(day) {
            const year = this.currentDate.getFullYear();
            const month = this.currentDate.getMonth();
            const date = new Date(year, month, day);

            return this.selectedDate && this.selectedDate.toDateString() === date.toDateString();
        },

        selectDate(day) {
            const year = this.currentDate.getFullYear();
            const month = this.currentDate.getMonth();
            this.selectedDate = new Date(year, month, day);
        },
    },
};
</script>

<style></style> -->
