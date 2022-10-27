<template>
  <div class="bg-gradient-to-r from-blue-900 to-red-700">
    <nav class="container py-2 mx-auto md:flex md:justify-between md:items-center">
      <div class="flex items-center justify-between">
        <NuxtLink to="/" class="text-xl font-bold text-gray-100 md:text-2xl hover:text-indigo-400">
          <img src="@/assets/images/GasBuss.png" class="rounded-full scale-100" width="70px" />
        </NuxtLink>
        <!-- Mobile menu button -->
        <div @click="toggleNav" class="flex md:hidden">
          <button type="button" class="text-gray-100 hover:text-gray-400 focus:outline-none focus:text-gray-400">
            <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
              <path
                fill-rule="evenodd"
                d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
              ></path>
            </svg>
          </button>
        </div>
      </div>

      <!-- Mobile Menu open: "block", Menu closed: "hidden" -->
      <ul
        :class="showMenu ? 'flex' : 'hidden'"
        class="flex-col mt-8 space-y-4 md:flex md:space-y-0 md:flex-row md:items-center md:space-x-10 md:mt-0"
      >
        <NuxtLink to="/" class="pl-2 text-white">Home</NuxtLink>
      </ul>
    </nav>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const showMenu = ref(false);
const toggleNav = () => (showMenu.value = !showMenu.value);
</script>

<style scoped></style>
