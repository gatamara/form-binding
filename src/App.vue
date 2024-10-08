<script setup>
import { ref } from 'vue';

const title = ref('');
const emoji = ref('😊');
const apreciacion = ref('Increíble');
const competenciasAprendidas = ref([
  'Morfología de un componente',
  'One-Way y Two-Way data binding',
  'El patrón de diseño MVVM',
]);
const opinion = ref('Ahora podré desarrollar aplicaciones más cómodamente!!');
</script>

<template>
  <div id="app" class="container my-4 ">
    <div class="row">

      <div class="col-md-5 p-4 bg-dark text-white rounded">
        <div class="mb-3">
          <label class="form-label">Título:</label>
          <input v-model="title" class="form-control" placeholder="Estoy aprendiendo Vue" />
        </div>

        <div class="mb-3">
          <label class="form-label">Emoji:</label>
          <select v-model="emoji" class="form-select">
            <option value="😊">😊</option>
            <option value="👍">👍</option>
            <option value="🚀">🚀</option>
          </select>
        </div>

        <h5>Apreciación:</h5>
        <div class="mb-3">
          <div class="form-check">
            <input type="radio" v-model="apreciacion" value="Regular" class="form-check-input" />
            <label class="form-check-label">Regular</label>
          </div>
          <div class="form-check">
            <input type="radio" v-model="apreciacion" value="Bien" class="form-check-input" />
            <label class="form-check-label">Bien</label>
          </div>
          <div class="form-check">
            <input type="radio" v-model="apreciacion" value="Muy bien" class="form-check-input" />
            <label class="form-check-label">Muy bien</label>
          </div>
          <div class="form-check">
            <input type="radio" v-model="apreciacion" value="Increíble" class="form-check-input" />
            <label class="form-check-label">Increíble</label>
          </div>
        </div>

        <h5>Competencias aprendidas:</h5>
        <div class="mb-3">
          <div class="form-check">
            <input type="checkbox" value="Morfología de un componente" v-model="competenciasAprendidas"
              class="form-check-input" />
            <label class="form-check-label">Morfología de un componente</label>
          </div>
          <div class="form-check">
            <input type="checkbox" value="One-Way y Two-Way data binding" v-model="competenciasAprendidas"
              class="form-check-input" />
            <label class="form-check-label">One-Way y Two-Way data binding</label>
          </div>
          <div class="form-check">
            <input type="checkbox" value="El patron de diseño MVVM" v-model="competenciasAprendidas"
              class="form-check-input" />
            <label class="form-check-label">El patrón de diseño MVVM</label>
          </div>
          <div class="form-check">
            <input type="checkbox" value="Directivas" v-model="competenciasAprendidas" class="form-check-input" />
            <label class="form-check-label">Directivas</label>
          </div>
          <div class="form-check">
            <input type="checkbox" value="Estado" v-model="competenciasAprendidas" class="form-check-input" />
            <label class="form-check-label">Estado</label>
          </div>
        </div>

        <div class="mb-3">
          <label class="form-label">Opinión:</label>
          <textarea v-model="opinion" class="form-control" rows="3"
            placeholder="Ahora podré desarrollar aplicaciones más cómodamente!!"></textarea>
        </div>
      </div>


      <div class="col-md-6 p-4">
        <div class="border rounded p-3">
          <h3>{{ title }}</h3>
          <p>{{ emoji }}</p>
          <h4>Y me parece {{ apreciacion }}</h4>
          <p>He aprendido:</p>
          <ul>
            <li v-for="competencia in competenciasAprendidas" :key="competencia">{{ competencia }}</li>
          </ul>
          <h5>Mi opinión hasta ahora del framework es:</h5>
          <p>{{ opinion }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
