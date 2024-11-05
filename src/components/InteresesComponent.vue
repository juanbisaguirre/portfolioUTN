<script setup>
import { ref } from 'vue';

var intereses = ref([
    {id:1, interes:'🍲 Cocinar:', descripcion: 'Pocas cosas me apacionan tanto como cocinar a mis seres queridos. A traves de la cocina puedo demostrar afecto a mis seres queridos.'},
    {id:2, interes:'🎮 Gaming:', descripcion: 'Disfruto mucho de un buen video juego, sin importar la plataforma, puede ser consola, PC, o mobile.'},
    {id:3, interes:'👨‍👧 Mi Familia:', descripcion: 'Cada tiempo libre que tengo, suelo invertirlo a mi Esposa e Hija, es de lo que mas disfruto hacer.'}
]);

</script>

<template>
    <div class="intereses-contenedor">
        <ul class="contenedor-lista">
            <li class="item" v-for="inte in intereses" :key="inte.id">
                 <span class="negrita">{{ inte.interes }}</span> {{ inte.descripcion }}
            </li>
        </ul>
    </div>
</template>

<style scoped>
.negrita {
    font-weight: bold; /* Asegura que el texto esté en negrita */
}

.intereses-contenedor {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 auto;
    max-width: 85%;
    padding: 2rem;
    background-color: #f0f0f0; /* Fondo gris muy claro */
    border-radius: 10px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1); /* Sombra suave */
}

.contenedor-lista {
    list-style-type: none;
    padding: 0;
    margin: 0;
    color: #333333; /* Texto gris oscuro */
    font-size: 1.4rem;
    text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3); /* Sombra de texto ligera */
}

.item {
    margin-bottom: 1rem;
    transition: transform 0.3s, color 0.3s, background-color 0.3s;
    padding: 0.5rem;
    border-radius: 5px;
}

.item:hover {
    transform: translateY(-3px); /* Levanta el elemento al hacer hover */
    color: #666666; /* Texto gris medio en hover */
    background-color: rgba(0, 0, 0, 0.1); /* Fondo gris claro en hover */
}
</style>
