<script setup>
import { ref } from 'vue';
const fechaColor = ref([
  { color: '#333333' }, // Gris oscuro
  { color: '#666666' }, // Gris medio oscuro
  { color: '#999999' }, // Gris medio
  { color: '#cccccc' }, // Gris claro
  { color: '#e0e0e0' }  // Gris muy claro
]);

const educacion = ref([
  {fecha: '2024/2025', title: 'Técnicatura Universitaria en Programación', descripcion: 'Incumbencias Profesionales: Operación y programación de computadoras, desarrollo de programas en distintos lenguajes, análisis y control de sistemas informáticos.', enlace:'https://www.youtube.com/@arielbetancud'},
  {fecha: '2022/2023', title: 'Desarrollador Web Full Stack', descripcion: 'Competencias profesionales: Desarrollo full-Stack JavaScript realizada en CoderHouse.Programacion Orientada a Objetos, HTML, CSS, DOM, express, NodeJS, MongoDB.', enlace:'https://www.coderhouse.com/ar/online/javascript'},
  {fecha: '2021/2022', title: 'Desarrollador Web Full Stack', descripcion: 'Competencias profesionales: Desarrollo full-Stack Java realizada en Egg Academy.Programacion Orientada a Objetos, HTML, CSS, Spring boot, MySQL.', enlace:'https://egg.live/es/home'}
]);
</script>

<template>
    <ul>
        <li v-for="(item, index) in educacion" :key="index" :style="{ '--fecha-color': fechaColor[index].color}">
            <div class="fecha">{{ item.fecha }}</div>
            <h3 class="title">{{ item.title }}</h3>
            <div class="descripcion">{{ item.descripcion }}</div>
            <a class="enlace" :href="item.enlace" target="_blank">Saber más</a>
        </li>
    </ul>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap");

*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  --color: #000000; /* Color de texto principal en negro */
  --bgColor: #ffffff; /* Fondo en blanco */
  min-height: 100vh;
  display: grid;
  align-content: center;
  gap: 2rem;
  padding: 2rem;
  font-family: "Poppins", sans-serif;
  color: var(--color);
  background: var(--bgColor);
}

ul {
  margin-top: 2rem;
  --col-gap: 2rem;
  --row-gap: 2rem;
  --line-w: 0.25rem;
  display: grid;
  grid-template-columns: var(--line-w) 1fr;
  grid-auto-columns: max-content;
  column-gap: var(--col-gap);
  list-style: none;
  width: min(60rem, 90%);
  margin-inline: auto;
}

ul::before {
  content: "";
  grid-column: 1;
  grid-row: 1 / span 20;
  background: #cccccc; /* Gris claro */
  border-radius: calc(var(--line-w) / 2);
}

ul li {
  grid-column: 2;
  --inlineP: 1.5rem;
  margin-inline: var(--inlineP);
  grid-row: span 3;
  display: grid;
  grid-template-rows: min-content min-content min-content;
  background: #f0f0f0; /* Fondo gris muy claro */
  border-radius: 8px;
  padding: 1rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1); /* Sombra ligera */
}

ul li .fecha {
  --dateH: 3rem;
  height: var(--dateH);
  margin-inline: calc(var(--inlineP) * -1);
  text-align: center;
  background-color: var(--fecha-color); /* Colores en diferentes tonos de gris */
  color: #ffffff; /* Texto blanco */
  font-size: 1.25rem;
  font-weight: 700;
  display: grid;
  place-content: center;
  position: relative;
  border-radius: calc(var(--dateH) / 2) 0 0 calc(var(--dateH) / 2);
}

.title {
  color: #000000; /* Título en negro */
  font-weight: 500;
  padding-inline: 1.5rem;
  background: #ffffff; /* Fondo blanco */
}

.descripcion {
  color: #333333; /* Texto gris oscuro */
  font-weight: 300;
  padding-inline: 1.5rem;
  background: #ffffff; /* Fondo blanco */
}

.enlace {
  color: #000000; /* Enlace en negro */
  text-decoration: none;
}

.enlace:hover {
  text-decoration: underline; /* Subrayado al pasar el mouse */
}

@media (min-width: 40rem) {
  ul {
    grid-template-columns: 1fr var(--line-w) 1fr;
  }
  ul::before {
    grid-column: 2;
  }
  ul li:nth-child(odd) {
    grid-column: 1;
  }
  ul li:nth-child(even) {
    grid-column: 3;
  }
  ul li:nth-child(2) {
    grid-row:2/4;
  }
  ul li:nth-child(odd) .fecha {
    border-radius: 0 calc(var(--dateH) / 2) calc(var(--dateH) / 2) 0;
  }
}
</style>
