<template>
<div class="vid-container">
                
                <video src="https://papiquieropizzaya.com/video-pizza-pagina.mp4" controls class="vid">Tu navegador no soporta o no ha podido cargar archivos .mp4 (Videos)</video>

</div>
</template>


<style>
.vid {
    width: 100%;
    border-style: ridge;
    border-radius: 10px;
}
.vid-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
@media (min-width: 768px) {
    .vid {
        width: 60%;
        border-style: ridge;
        border-radius: 10px;
        align-tracks: center;
    }
}
</style>