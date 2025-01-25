<template>
  <div ref="loader-wrapper" id="loader-wrapper" v-if="showLoader">
    <div id="loader">
      <img src="./img/loader-wrapper/pizza.png" alt="Cargando...">
    </div>
    <p id="connection-warning" v-if="showWarning">Verifica tu conexión a internet.</p>
  </div>
</template>

<script setup lang="ts">

const loaderElement = useTemplateRef("loader-wrapper")

// Variables reactivas
const showLoader = ref(true); // Controla la visibilidad del loader
const showWarning = ref(false); // Controla la visibilidad del mensaje de advertencia

onMounted(() => {

  window.addEventListener("load", function() {
    const loader = document.getElementById("loader");
    const warning = document.getElementById("connection-warning");

    // Mostrar advertencia después de 4 segundos si la página sigue cargando
    const warningTimeout = setTimeout(function() {
        warning.style.display = "block";
    }, 4000);

    loader.addEventListener("animationiteration", function() {
        // Una vez que se complete la vuelta actual, realiza la transición hacia arriba
        loaderElement.value!.style.transform = "translateY(-100%)"; // Mueve el fondo hacia arriba
        document.getElementById("content").style.display = "block"; // Muestra el contenido
        
        // Cancela el mensaje de advertencia si ya cargó
        clearTimeout(warningTimeout);

        // Espera 1 segundo para que la transición termine antes de ocultar el wrapper
        setTimeout(function() {
            showLoader.value = false; // Oculta el loader
        }, 1000);
    });

    // Desactiva la animación infinita cuando la página está completamente cargada
    loader.style.animationIterationCount = "1";
});});

</script>

<style>
#loader-wrapper {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #F9E0AE;
  z-index: 9999;
  transition: transform 1s ease-in-out;
}

#loader img {
  width: 100px;
  height: 100px;
  animation: spin infinite 1s linear;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

#connection-warning {
  margin-top: 20px;
  font-size: 18px;
  color: red;
  text-align: center;
}
</style>

