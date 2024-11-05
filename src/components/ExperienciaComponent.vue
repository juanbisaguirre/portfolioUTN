<script setup>
import pencil from '/src/assets/pencil.svg';
import llave from '/src/assets/wrench-13-svgrepo-com.svg';
import desarrolloWeb from '/src/assets/desarrolloWeb.svg';
import ccv from '/src/assets/cv.svg';
import libro from '/src/assets/libro.svg';

import { ref } from 'vue';

const titulo ='Desarrollador Web y Tecnico en microelectronica';
const fecha = 'Desde Abril 2022 / Actualidad';
const experiencias = ref([
    {id:1, src: pencil, parrafo: 'Diagnosticar fallas a nivel hardware o software en disposirivos moviles'},
    {id:2, src: llave, parrafo: 'Elaboracion de Presupuestos y reparacion de dispositivos moviles a nivel hardware y software.'},
    {id:3, src: desarrolloWeb, parrafo: 'Analisis de requerimientos, y Desarrollo de Paginas Web o E-commers a medida.'},
    {id:4, src: ccv, parrafo: 'Testeo de Pagina y Correccion de errores para un producto eficiente.'},
    {id:5, src: libro, parrafo: 'Escribir Documentacion del proyecto solicitado.'}
])
</script>

<template>
    <div class="card">
        <h3 class="titulo">{{ titulo }}</h3>
        <p class="fecha">{{ fecha }}</p>
        <ul class="item" v-for="experiencia in experiencias" :key="experiencia.id">
            <img class="imagen-svg" :src="experiencia.src" width="45rem" :alt="experiencia.parrafo">
            <p>{{ experiencia.parrafo }}</p>
        </ul>
    </div>
</template>

<style scoped>
.card {
    display: flex;
    flex-direction: column;
    padding: 2rem;
    background-color: #ffffff; /* Fondo blanco */
    border-radius: 15px;
    box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.2); /* Sombra gris suave */
}

.titulo {
    font-size: 1.5rem;
    color: #333333; /* Texto gris oscuro */
}

.fecha {
    font-size: 1rem;
    color: #555555; /* Texto gris medio */
    margin-bottom: 1rem;
}

.listado {
    display: flex;
    flex-direction: column;
}

.item {
    align-items: center;
    display: flex;
    padding: 1rem;
    gap: 1.5rem;
    background-color: #f0f0f0; /* Fondo gris claro */
    border-radius: 10px;
    color: #333333; /* Texto gris oscuro */
}

h3 {
    font-weight: bold;
}
</style>

