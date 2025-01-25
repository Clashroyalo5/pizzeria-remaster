<template>
        <nav id="navbar" class="navbar">
            <div class="logo">
                <a href="#">
                    <img src="https://papiquieropizzaya.com/Icon.png" alt="Logo" class="logo-img">
                </a>
            </div>
            <ul class="nav-links">
                <li><a href="#home">Inicio</a></li>                
                <li><a href="#menu">Menú link 1</a></li>
                <li><a href="https://papiquieropizzaya.com/menu/" target="_parent">Menú link 2</a></li>
                <li><a href="#inf">Info de cada pizza</a></li>                
                <li><a href="https://papiquieropizzaya.com/pedido-en-linea/">Haz tu pedido en linea</a></li>
                <li><a href="#about">Acerca de</a></li>

            </ul>
            <div class="burger">
                <div class="line1"></div>
                <div class="line2"></div>
                <div class="line3"></div>
            </div>
        </nav>
</template>

<style>
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #333;
    padding: 10px 20px;
    position: fixed; /* Cambiado a fixed para que se mantenga visible */
    top: 0;
    width: 100%;
    z-index: 1000; /* Asegura que la navbar esté por encima de otros elementos */
    transition: top 0.3s; /* Añade una transición suave para mostrar/ocultar la navbar */
}

.navbar-hidden {
    top: -100px; /* Ajusta este valor según la altura de tu navbar */
}

.logo img {
    height: 50px; /* Ajusta el tamaño del logo aquí */
}

.nav-links {
    list-style: none;
    display: flex;
}

.nav-links li {
    margin-left: 20px;
}

.nav-links a {
    color: rgb(252, 0, 0);
    text-decoration: none;
    font-size: 18px;
    background-color: rgba(0, 0, 0, 0);
}

.nav-links a:hover {
    color: #f4b400;
}

.burger {
    display: none;
    cursor: url('pizza-cursor-3.png'), auto;
}

.burger div {
    width: 25px;
    height: 3px;
    background-color: white;
    margin: 5px;
    transition: all 0.3s ease;
}

@media screen and (max-width: 768px) {

    .nav-links {
        position: absolute;
        right: 0;
        height: 100vh;
        top: 70px; /* Establece la distancia desde la parte superior de la pantalla */
        background-color: #333;
        display: flex;
        flex-direction: column;
        align-items: center;
        min-width: 235px;
        width: 50%;
        transform: translateX(100%);
        transition: transform 0.5s ease-in;
        z-index: 1000; /* Asegura que la navbar esté por encima de otros elementos */
    }

    .nav-links li {
        opacity: 0;
        margin-bottom: 30px; /* Añade más separación entre los elementos */
    }

    .burger {
        display: block;
    }

    .nav-active {
        transform: translateX(0);
    }

    .nav-active li {
        opacity: 1;
        transition: opacity 0.5s ease-in-out;
        transition-delay: 0.3s;
    }

    .toggle .line1 {
        transform: rotate(-45deg) translate(-5px, 6px);
    }

    .toggle .line2 {
        opacity: 0;
    }

    .toggle .line3 {
        transform: rotate(45deg) translate(-5px, -6px);
    }

}
</style>

<script setup lang="ts">

onMounted (()=> {
    const burger = document.querySelector('.burger');
    const nav = document.querySelector('.nav-links');
    const navLinks = document.querySelectorAll('.nav-links li');

    burger.addEventListener('click', () => {
        // Toggle Nav
        nav.classList.toggle('nav-active');

        // Animate Links
        navLinks.forEach((link, index) => {
            if (link.style.animation) {
                link.style.animation = '';
            } else {
                link.style.animation = `navLinkFade 0.5s ease forwards ${index / 7 + 0.3}s`;
            }
        });

        // Burger Animation
        burger.classList.toggle('toggle');
    });







    const navbar = document.getElementById('navbar');
    let lastScrollTop = 0;

    window.addEventListener('scroll', () => {
        let scrollTop = window.pageYOffset || document.documentElement.scrollTop;

        if (scrollTop > lastScrollTop) {
            // Scroll hacia abajo, esconder navbar
            navbar.classList.add('navbar-hidden');
        } else {
            // Scroll hacia arriba, mostrar navbar
            navbar.classList.remove('navbar-hidden');
        }

        lastScrollTop = scrollTop <= 0 ? 0 : scrollTop; // Evita que lastScrollTop sea negativo
    });
    });
</script>