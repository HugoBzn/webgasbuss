<template>
  <div class="px-6 py-6">
    <Servicios
      @receivedData="
        (payload) => {
          list = payload;
        }
      "
    />
    <div v-for="item in list" class="border border-purple-600 rounded-lg p-3 mb-3">
      <div class="grid lg:grid-cols-4 md:grid-cols-1">
        <div>
          <p class="font-bold">
            {{ item.Nombre }}
          </p>
        </div>
        <div>
          {{ item.Clase_actividad }}
        </div>
        <div>
          {{ item.Ubicacion }}
        </div>
        <div>
          {{ item.Longitud }}
          {{ item.Latitud }}
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Servicios from '../components/Servicios.vue';

const list = ref([]);
</script>

<style lang="scss" scoped></style>
