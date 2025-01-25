<template>
  <LoaderWrapper />
  

  <!-- Contenido principal, se muestra solo cuando el loader desaparece -->
  <div id="content" style="display: block;">
    
    <Welcome />
  </div>
</template>

<script setup lang="ts">

import Welcome from "./components/welcome.vue"; // Importa el componente Welcome
</script>
