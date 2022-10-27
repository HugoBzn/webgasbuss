<template>
  <div class="px-6 py-6">
    <div class="grid grid-cols-2 gap-4">
      <div class="border border-blue-600 rounded-lg">
        <p></p>
      </div>
      <div class="border border-red-600 rounded-lg">
        <p class="text-center font-bold">Directorio</p>
        <img src="@/assets/images/notebook.gif" />
        <div class="grid grid-cols-6">
          <NuxtLink
            class="col-start-3 col-end-5 mb-4 transition duration-300 ease-in-out centertext-white bg-gradient-to-br from-purple-600 to-blue-500 hover:bg-gradient-to-bl focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center"
            to="/directorio"
          >
            Ir al Directorio
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup></script>

<style scoped></style>
