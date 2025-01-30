<template>
<div class="carousel-container">
            <div class="carousel">
                <ul>

                    <li><img src="https://papiquieropizzaya.com/Carrusel/5.jpg" alt="Imagen 2" ></li>

                    <li><img src="https://papiquieropizzaya.com/papi%20quiero%20pizza%20ya%20imagen.png" alt="Nose"></li>

                    <li><img src="https://papiquieropizzaya.com/Carrusel/0.jpg" alt="Imagen 4"></li>

                    <li><img src="https://papiquieropizzaya.com/Carrusel/3.jpg" alt="Imagen 3"></li>
                    
                    <li><img src="https://papiquieropizzaya.com/Carrusel/6.jpg" alt="Imagen 1"></li>

                    <li><img src="https://papiquieropizzaya.com/Carrusel/8.jpg" alt="Imagen 1"></li>

                </ul>
            </div>
        </div>
</template>

<script setup lang="ts">

onMounted (() => {

    let currentIndex = 0;
const slides = document.querySelectorAll('.carousel ul li');
const totalSlides = slides.length;

function moveSlide() {
    currentIndex = (currentIndex + 1) % totalSlides;
    const translateValue = -currentIndex * 100 + '%';
    document.querySelector('.carousel ul').style.transform = `translateX(${translateValue})`;


}

setInterval(moveSlide, 4500); // Cambia de imagen cada 4,5 segundos




});

</script>

<style>
.carousel {
    max-width: 60%;
    overflow: hidden;
    position: relative;
    border-radius: 14px;
}

.carousel ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    transition: transform 1s ease-in-out;
}

.carousel ul li {
    flex: 0 0 auto;
    width: 100%; /* Asegura que cada imagen ocupe el 100% del ancho */
}

.carousel img {
    width: 100%;
    display: block;
}

.carousel-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

@media (min-width: 1000px) {
    
    .carousel {
        width: 100%;
        overflow: hidden;
        position: relative;
        border-radius: 14px;
    }
}
</style>