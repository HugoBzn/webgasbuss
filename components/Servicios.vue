<template>
  <div class="px-6 py-6">
    <form @submit.prevent="getData" id="form">
      <div class="grid gap-6 mb-6 lg:grid-cols-2 md:grid-cols-1">
        <div>
          <label for="condicion" class="block mb-2 text-sm font-medium text-white">Condición</label>
          <input
            type="text"
            id="condicion"
            class="bg-gray-50 border border-gray-300 text-black text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
            placeholder="Restaurante"
            required
            v-model="condicion"
          />
        </div>
        <div>
          <label for="Latitud" class="block mb-2 text-sm font-medium text-white">Latitud</label>
          <input
            type="text"
            id="Latitud"
            class="bg-gray-50 border border-gray-300 text-black text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
            placeholder="24.0346737"
            required
            v-model="latitud"
          />
        </div>
        <div>
          <label for="Longitud" class="block mb-2 text-sm font-medium text-white">Longitud</label>
          <input
            type="text"
            id="Longitud"
            class="bg-gray-50 border border-gray-300 text-black text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
            placeholder="-104.6818207"
            required
            v-model="longitud"
          />
        </div>
        <div>
          <label for="metros" class="block mb-2 text-sm font-medium text-white">Metros</label>
          <input
            type="text"
            id="metros"
            class="bg-gray-50 border border-gray-300 text-black text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5"
            placeholder="300"
            required
            v-model="metros"
          />
        </div>
      </div>
      <button
        type="submit"
        class="mt-16 col-start-3 col-end-5 mb-4 transition duration-300 ease-in-out centertext-white bg-gradient-to-br from-purple-600 to-blue-500 hover:bg-gradient-to-bl focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center"
      >
        Ver listado
      </button>
      <button
        class="mt-16 col-start-3 col-end-5 mb-4 transition duration-300 ease-in-out centertext-white bg-gradient-to-br from-purple-600 to-blue-500 hover:bg-gradient-to-bl focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center"
        @click="urlAPI"
      >
        Armar
      </button>
    </form>
  </div>
</template>

<script setup>
import axios from 'axios';
import { ref } from 'vue';

const token = ref('08fd1e11-a8d8-4c34-867f-8bb5df311f97');

const condicion = ref('');
const latitud = ref();
const longitud = ref();
const metros = ref();

const data = ref('');

const url = ref('');

// Armando la URL dinamica
const urlAPI = () => {
  url.value = `https://www.inegi.org.mx/app/api/denue/v1/consulta/buscar/${condicion.value}/${latitud.value},${longitud.value}/${metros.value}/${token.value}`;
};

const emit = defineEmits(['receivedData']);

// Metodo GET
const getData = async () => {
  const res = await axios.get(url.value);
  emit('receivedData', res.data);
};
</script>
