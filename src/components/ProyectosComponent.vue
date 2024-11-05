<script setup>
import chat from '/src/assets/chat.svg';
import apiCrud from '/src/assets/apiCrud.svg';
import calculadora from '/src/assets/calculadora.svg'
import { ref } from 'vue';

var proyectos = ref([]);

proyectos.value = ([
    {nombre: 'Chat', descripcion: 'App web de chat hecha con express, handlebars y socket.io', git:'https://github.com/juanbisaguirre/app_chat_websockets', imagen: chat}, 
    {nombre: 'Api Crud' , descripcion: 'Desarrollo de una API-CRUD en NodeJS', git:'https://github.com/juanbisaguirre/1eraAPI', imagen: apiCrud},
    {nombre: 'Calculadora' , descripcion: 'Desarrollo de una calculadora con solo una linea de JavaScript y HTML y CSS', git:'https://github.com/juanbisaguirre/calculadora', imagen: calculadora}
    
]);
</script>

<template>
    <div class="galeria">
        <div class="proyecto" v-for="(proyecto, index) in proyectos" :key="index">
            <img class="imagen-proyecto" :src="proyecto.imagen" :alt="`Imagen del proyecto ${proyecto.nombre}`">
            <div class="proyecto-info">
                <h3>{{ proyecto.nombre }}</h3>
                <p>{{ proyecto.descripcion }}</p>
                <div class="proyecto-links">
                    <a :href="proyecto.git" class="btn-ver-mas" target="_blank" rel="noopener noreferrer">Ver Código en GitHub</a>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.galeria {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
    background-color: #f0f0f0; /* Fondo gris claro */
    width: 100%;
    height: 100vh;
}

.imagen-proyecto {
    width: 100%; /* Asegura que la imagen ocupe el ancho completo del contenedor */
    height: 200px; /* Define un alto fijo para las imágenes */
    object-fit: cover; /* Recorta la imagen para que llene el área sin distorsión */
}

.proyecto {
    display: flex;
    flex-direction: column;
    border: 2px solid #cccccc; /* Borde gris */
    border-radius: 8px;
    overflow: hidden;
    background-color: #ffffff; /* Fondo blanco */
    max-width: 300px; /* Define el ancho máximo */
    width: 100%; /* Ocupa el 100% del ancho disponible dentro del contenedor */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease;
}

.proyecto:hover {
    transform: translateY(-5px); /* Efecto elevación */
}

.proyecto img {
    width: 100%;
    height: auto;
    display: block;
}

.proyecto-info {
    padding: 15px;
    text-align: center;
}

.proyecto-info h3 {
    margin: 10px 0;
    font-size: 1.3em;
    color: #333333; /* Texto gris oscuro */
}

.proyecto-info p {
    margin: 10px 0;
    font-size: 1em;
    color: #555555; /* Texto gris medio */
}

.proyecto-links {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 10px;
}

.proyecto-links .btn-ver-mas {
    background-color: #333333; /* Fondo negro */
    color: #ffffff; /* Texto blanco */
    padding: 10px 15px;
    border-radius: 5px;
    text-decoration: none;
    transition: background-color 0.3s;
}

.proyecto-links .btn-ver-mas:hover {
    background-color: #222222; /* Negro más oscuro */
}

.proyecto-links .github-link {
    color: #666666; /* Texto gris */
    text-decoration: none;
    font-size: 0.9em;
}

.proyecto-links .github-link:hover {
    text-decoration: underline;
}
</style>
