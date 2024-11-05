<script setup>
import {ref} from 'vue';
const navegacion = ref([
    {id: 1, nombre: 'Educación', enlace: '#educacion'},
    {id: 2, nombre: 'Experiencia', enlace: '#experiencia'},
    {id: 3, nombre: 'Proyectos', enlace: '#proyectos'},
    {id: 4, nombre: 'Habilidades', enlace: '#habilidades'},
    {id: 5, nombre: 'Intereses', enlace: '#intereses'},
]);
</script>

<template>
    <nav class="navbar">
        <div class="navbar-menu">
            <ul>
                <a v-for="nav in navegacion" :key="nav.id" :href="nav.enlace" class="nav-item">{{ nav.nombre }}</a>
            </ul>
        </div>
    </nav>
</template>

<style scoped>
.navbar {
    background-color: #ffffff; /* Blanco para la barra de navegación */
    padding: 0.75rem 1.5rem;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.5); /* Sombra en negro */
    display: flex;
    justify-content: flex-end;
    align-items: center;
}

.nav-item {
    color: #000000; /* Negro para el texto */
    text-decoration: none;
    margin-right: 1.5rem;
    font-weight: 600;
    border: 2px solid transparent;
    border-radius: 5px;
    padding: 0.5rem 1rem;
    transition: background-color 0.3s ease, border-color 0.3s ease;
}

.nav-item:hover {
    background-color: #979797; /* Gris medio al hacer hover */
    border-color: #e0e0e0; /* Borde gris claro al hacer hover */
}

.navbar-menu ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: flex-end;
}

@media (max-width: 768px) {
    .navbar-menu {
        width: 100%;
    }

    .nav-item {
        margin-right: 0.5rem;
    }
}
</style>
