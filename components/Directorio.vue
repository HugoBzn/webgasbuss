<template>
  <div class="px-6 py-6">
    <div class="grid grid-cols-1 gap-4">
      <!-- First Card -->
      <div class="border border-purple-600 rounded-lg p-3">
        <div class="grid lg:grid-cols-3 md:grid-cols-1">
          <div>
            <p class="font-bold">Sucursal</p>
            <p>CEDIS Saltillo</p>
            <p class="font-bold">División GE</p>
            <p>Norte</p>
            <p class="font-bold">Región GE</p>
            <p>Saltillo</p>
            <p class="font-bold">Zona Administrativa</p>
            <p>Coahuila-Durango</p>
          </div>
          <div>
            <p class="font-bold">Telefono</p>
            <p>(844) 4168663 / Ext. Interna 700 700 1770</p>
            <p>(844) 4165687 / Ext. Interna 700 700 1771</p>
            <p class="font-bold">Ciudad</p>
            <p>Saltillo</p>
            <p class="font-bold">Estado</p>
            <p>Coahuila</p>
          </div>
          <div class="border rounded-lg">
            <div id="mapContainer01"></div>
          </div>
        </div>
      </div>

      <!-- Second card -->
      <div class="border border-purple-600 rounded-lg p-3">
        <div class="grid lg:grid-cols-3 md:grid-cols-1">
          <div>
            <p class="font-bold">Sucursal</p>
            <p>CEDIS Chihuahua</p>
            <p class="font-bold">División GE</p>
            <p>Norte</p>
            <p class="font-bold">Región GE</p>
            <p>Chihuahua</p>
            <p class="font-bold">Zona Administrativa</p>
            <p>Chihuahua</p>
          </div>
          <div>
            <p class="font-bold">Telefono</p>
            <p>(614) 4243010 / Ext. Interna 700 700 4500</p>
            <p>(614) 4243011 / (614) 4243065</p>
            <p class="font-bold">Ciudad</p>
            <p>Chihuahua</p>
            <p class="font-bold">Estado</p>
            <p>Chihuahua</p>
          </div>
          <div class="border rounded-lg">
            <div id="mapContainer02"></div>
          </div>
        </div>
      </div>

      <!-- Third card -->
      <div class="border border-purple-600 rounded-lg p-3">
        <div class="grid lg:grid-cols-3 md:grid-cols-1">
          <div>
            <p class="font-bold">Sucursal</p>
            <p>CEDIS Veracruz</p>
            <p class="font-bold">División GE</p>
            <p>Sureste</p>
            <p class="font-bold">Región GE</p>
            <p>Golfo Sur</p>
            <p class="font-bold">Zona Administrativa</p>
            <p>Golfo Sur</p>
          </div>
          <div>
            <p class="font-bold">Telefono</p>
            <p>(229) 9896110 al (229)9896140 /Ext. Interna 5360 al 5399.</p>
            <p class="font-bold">Ciudad</p>
            <p>Veracruz</p>
            <p class="font-bold">Estado</p>
            <p>Veracruz</p>
          </div>
          <div class="border rounded-lg">
            <div id="mapContainer03"></div>
          </div>
        </div>
      </div>

      <!-- Fourth card -->
      <div class="border border-purple-600 rounded-lg p-3">
        <div class="grid lg:grid-cols-3 md:grid-cols-1">
          <div>
            <p class="font-bold">Sucursal</p>
            <p>CEDIS Villahermosa</p>
            <p class="font-bold">División GE</p>
            <p>Sureste</p>
            <p class="font-bold">Región GE</p>
            <p>Tabasco</p>
            <p class="font-bold">Zona Administrativa</p>
            <p>Tabasco - Chiapas</p>
          </div>
          <div>
            <p class="font-bold">Telefono</p>
            <p>(933) 358 1400 / Ext. Interna 700 700 1400</p>
            <p class="font-bold">Ciudad</p>
            <p>Villahermosa</p>
            <p class="font-bold">Estado</p>
            <p>Tabasco</p>
          </div>
          <div class="border rounded-lg">
            <div id="mapContainer04"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted } from 'vue';

// Primer tarjeta
const center01 = [25.4561644, -101.0122757];
const setupLeafletMap01 = () => {
  const mapDiv = L.map('mapContainer01').setView(center01, 13);

  L.tileLayer('http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution:
      'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, <a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="http://cloudmade.com">CloudMade</a>',
    maxZoom: 18,
  }).addTo(mapDiv);

  L.control.scale().addTo(mapDiv);
  L.marker([25.4561644, -101.0122757], { draggable: true }).addTo(mapDiv);

  L.marker([25.4561644, -101.0122757]).addTo(mapDiv).bindPopup('CEDIS Saltillo.').closePopup();
};

// Segunda tarjeta
const center02 = [28.6915615, -106.0893669];
const setupLeafletMap02 = () => {
  const mapDiv = L.map('mapContainer02').setView(center02, 13);

  L.tileLayer('http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution:
      'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, <a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="http://cloudmade.com">CloudMade</a>',
    maxZoom: 18,
  }).addTo(mapDiv);

  L.control.scale().addTo(mapDiv);
  L.marker([28.6915615, -106.0893669], { draggable: true }).addTo(mapDiv);

  L.marker([28.6915615, -106.0893669]).addTo(mapDiv).bindPopup('CEDIS Chihuahua.').closePopup();
};

// Tercera tarjeta
const center03 = [19.1654183, -96.2278603];
const setupLeafletMap03 = () => {
  const mapDiv = L.map('mapContainer03').setView(center03, 13);

  L.tileLayer('http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution:
      'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, <a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="http://cloudmade.com">CloudMade</a>',
    maxZoom: 18,
  }).addTo(mapDiv);

  L.control.scale().addTo(mapDiv);
  L.marker([19.1654183, -96.2278603], { draggable: true }).addTo(mapDiv);

  L.marker([19.1654183, -96.2278603]).addTo(mapDiv).bindPopup('CEDIS Veracruz.').closePopup();
};

// Tercera tarjeta
const center04 = [18.0283049, -92.9100223];
const setupLeafletMap04 = () => {
  const mapDiv = L.map('mapContainer04').setView(center04, 13);

  L.tileLayer('http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution:
      'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, <a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="http://cloudmade.com">CloudMade</a>',
    maxZoom: 18,
  }).addTo(mapDiv);

  L.control.scale().addTo(mapDiv);
  L.marker([18.0283049, -92.9100223], { draggable: true }).addTo(mapDiv);

  L.marker([18.0283049, -92.9100223]).addTo(mapDiv).bindPopup('CEDIS Villahermosa.').closePopup();
};

onMounted(() => {
  setupLeafletMap01();
  setupLeafletMap02();
  setupLeafletMap03();
  setupLeafletMap04();
});
</script>

<style scoped></style>
