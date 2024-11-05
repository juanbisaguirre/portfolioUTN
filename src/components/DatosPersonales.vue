<script setup>
import linkedin from '/src/assets/linkedin_icon.svg';
import instagram from '/src/assets/instagram_icon.svg';
import github from '/src/assets/github_icon.svg';
import cv from '/src/assets/cv_resume_icon.svg';
import fotomia from '/src/assets/juanbisaguirre.png';
const title = 'Juan A. Bisaguirre';
const descripcion = 'Técnico Universitario en Programación - UTN FRSR';
const residencia = 'Ciudad de Mendoza, Mendoza, Argentina';
const presentacion = '¡Hola! Bienvenido a mi portafolio de proyectos. Soy desarrollador web con experiencia en el desarrollo de aplicaciones web y móviles.';
const redesSociales = [
    { id: 1, name: 'linkedin', src: linkedin , url: 'https://www.linkedin.com/in/juan-anibal-bisaguirre-livellara/' },
    { id: 2, name: 'Instagram', src: instagram, url: 'https://www.instagram.com/bisatech.ok/profilecard/?igsh=MWFneW1nM3d5Y3BlYg==/' },
    { id: 3, name: 'github', src: github, url: 'https://github.com/juanbisaguirre' },
    { id: 4, name: 'curriculum', src: cv, url: 'https://drive.google.com/file/d/14rMcfgnCZRPzaHkkVY3vvodiF7ciDZBC/view?usp=sharing' },
];
const telefono = '+54 9 2615757869';
const photoUrl = fotomia; 
</script>

<template>
    <section class="datos-personales">
        <div class="card">
            <img :src="photoUrl" alt="Foto " class="foto" />
            <h1>{{ title }}</h1>
            <h2>{{ descripcion }}</h2>
            <p>{{ presentacion }}</p>
            <ul class="container-lista">
                <li v-for="red in redesSociales" :key="red.id">
                    <a :href="red.url" target="_blank">
                        <img class="icon-redsocial" :src="red.src" width="45rem" :alt="red.name">
                    </a>
                </li>
            </ul>
            <h3>☎ Mi Teléfono personal: {{ telefono }}</h3>
            <h4>{{ residencia }}</h4>
        </div>
    </section>
</template>

<style scoped>

h1 {
    font-size: 3.5rem;
    color: #333333; /* Gris oscuro */
    font-weight: bold;
    margin-bottom: 0.5rem;
    text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.4); /* Sombra en negro */
}

h2 {
    font-size: 2.2rem;
    color: #666666; /* Gris medio oscuro */
    margin-bottom: 1rem;
}

p {
    font-size: 1.3rem;
    font-weight: 500;
    color: #666666; /* Gris medio oscuro */
    margin-bottom: 2rem;
}

.card {
    background-color: #f0f0f0; /* Gris muy claro */
    border-radius: 15px;
    padding: 20px;
    margin: 10px;
    text-align: center;
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2); /* Sombra en negro */
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-10px); /* Efecto de elevación */
}

.foto {
    width: 250px;
    height: 250px;
    border-radius: 50%;
    margin-bottom: 1rem;
}

.container-lista {
    display: flex;
    justify-content: center;
    list-style: none;
    padding: 0;
    margin: 0 0 2rem 0;
}

.icon-redsocial {
    align-items: center;
    background-color: #e0e0e0; /* Gris claro */
    border-radius: 50%;
    padding: 8px;
    margin: 5px;
    box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1); /* Sombra en negro */
    transition: background-color 0.3s ease, transform 0.3s ease;
}

.icon-redsocial:hover {
    background-color: #b0b0b0; /* Gris medio */
    transform: scale(1.1);
}

h3 {
    font-size: 1.4rem;
    color: #333333; /* Gris oscuro */
    margin-bottom: 0.5rem;
}

h4 {
    font-size: 1.1rem;
    color: #666666; /* Gris medio oscuro */
}

.datos-personales {
    margin-top: 10px;
}

</style>
