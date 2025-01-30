<template>
  <LoaderWrapper />
  <!-- Contenido principal, se muestra solo cuando el loader desaparece -->
  <div id="content" style="display: block;">
    <Navbar />
    <Welcome />
    <Button1 />
    <Carrusel />
    <Direccion />
    <Vid />
    <Menus />
  </div>
</template>

<script setup lang="ts">

import Direccion from "./components/direccion.vue";
import Welcome from "./components/welcome.vue"; // Importa el componente Welcome


useHead({
  title: 'Papi Quiero Pizza Ya',
  meta: [
    { charset: 'UTF-8'},
    { name: 'google-site-verification', content: 'WfiA4hGyjafIAhHt9pbjUjHsb3ArnhuDPosnt4M6rSk' },
    { name: 'google-site-verification', content: 'HrH1EZzarEX74zAlEJfuaUTCc2pXb61NcfePXgdp_3U' },
    { name: 'viewport', content: 'width=device-width, initial-scale=1' },
    { name: 'keywords', content: 'papiquieropizzaya, Papi Quiero Pizza Ya, Papi quiero pizza ya, papi quiero pizza, Papi quiero pizza, Papi Quiero Pizza, Chinácota, chinácota, Chinacota, chinacota, Pizza Chinácota, Pizza chinácota, Pizza Chinacota, Pizza chinacota, pizza Chinácota, pizza chinácota, pizza Chinacota, pizza chinacota' },
    { name: 'description', content: 'My amazing site.' },
    { name: 'robots', content: 'index,follow' },
    { name: 'author', content: 'Abel Nicolás Jaimes Orjuela' },
  ],

  link: [
    { rel: 'preconnect', href: 'https://fonts.googleapis.com' },
    { rel: 'icon', href: './img/icon/Icon.png' },
    { rel: 'preconnect', href: 'https://fonts.gstatic.com' , crossorigin: true },
    { href: 'https://fonts.googleapis.com/css2?family=Special+Elite&display=swap', rel: 'stylesheet' },
    { href: 'https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap', rel: 'stylesheet' }
  ],

  script: [
    { async: true, src: 'https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-9448273062479555', crossorigin: 'anonymous' }
  ]
})
</script>




<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    cursor: url('./img/cursor/pizza-cursor-3.png'), auto;
}
body {
    
    background-image: url('./img/fondo/fondo-2.jpeg'); /* Reemplaza con la ruta real de tu imagen */
    background-repeat: repeat; /* Controla si la imagen se repite (opcional) */
    background-size: cover; /* Controla el tamaño de la imagen (opcional) */
    background-position: center; /* Controla la posición de la imagen (opcional) */
      background-attachment: fixed
    
}
body {
    font-family: "Poppins", sans-serif;
    font-weight: 100;
    font-style: normal;
}
.footer {
    text-align: center;
    padding: 30px solid #ffffffd5;
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
}
a {
    color: aqua;
    background-color: rgba(0, 0, 0, 0.5);
    text-decoration: none;
    transition: color 0.3s;
}
a:hover {
    color: crimson;
    background-color: rgba(0, 0, 0, 0.5);
    text-decoration: none;
}
hr {
    margin-top: 20px;
    margin-bottom: 20px;
}
</style>
