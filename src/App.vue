<script setup>
import NavBar from './components/NavBar.vue';
import DatosPersonales from './components/DatosPersonales.vue';
import EducacionComponent from './components/EducacionComponent.vue';
import ExperienciaComponent from './components/ExperienciaComponent.vue';
import ProyectosComponent from './components/ProyectosComponent.vue';
import HabilidadesComponent from './components/HabilidadesComponent.vue'; 
import InteresesComponent from './components/InteresesComponent.vue';
</script>

<template>
  <header id="top">
    <!-- Barra de navegación -->
    <NavBar/>
    <!-- Datos Personales -->
    <DatosPersonales/>
  </header>
  <main>
    <section id="educacion">
      <h2>Educación - Cursos</h2>
      <EducacionComponent/>
    </section>
    <section id="experiencia">
      <h2>Experiencia</h2>
      <ExperienciaComponent/>
    </section>
    <section id="proyectos">
      <h2>Proyectos</h2>
      <ProyectosComponent/>
    </section>
    <section id="habilidades">
      <h2>Habilidades</h2>
      <HabilidadesComponent/>
    </section>
    <section id="intereses">
      <h2>Intereses</h2>
      <InteresesComponent/>
    </section>
  </main>
  <footer>
  <a href="#top">
    <img src="/src/assets/logo-bisatech-FONDO-NEGRO_Mesa-de-trabajo1.png" alt="Logo" style="height: 45px; vertical-align: middle; margin-right: 8px;">
  </a>
  <p>© 2024 Juan Bisaguirre - Portafolio Web</p>
</footer>

</template>

<style scoped>
/* Estilos para los encabezados de sección */
section h2 {
    font-size: 2.5rem;
    color: #fffefe; /* Gris oscuro */
    font-weight: bold;
    text-align: center;
    margin-bottom: 1rem;
    padding-bottom: 0.5rem;
    position: relative;
    text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.5); /* Sombra en negro */
}

/* Línea decorativa debajo del h2 */
section h2::after {
    content: "";
    display: block;
    width: 50px;
    height: 4px;
    background-color: #666666; /* Gris medio */
    margin: 0.5rem auto 0;
    border-radius: 2px;
}



/* Espaciado entre la última sección y el footer */
section {
    margin-bottom: 4rem;
}

/* Estilos para el footer */
footer {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 2rem;
    font-size: 1.3rem;
    background-color: #e0e0e0; /* Gris claro para el fondo del footer */
    color: #333333; /* Gris oscuro para el texto */
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1); /* Sombra suave */
    border-top: 4px solid #666666; /* Borde superior en gris medio */
    text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3); /* Sombra ligera en el texto */
    margin-top: 4rem;
}

footer a {
    color: #555555; /* Gris medio oscuro para los enlaces */
    text-decoration: none;
    transition: color 0.3s;
}

footer a:hover {
    color: #999999; /* Gris claro en hover */
}
</style>
