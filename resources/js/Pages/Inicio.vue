<template>
    <div>
        <div class="row mt-3">
            <div id="carouselExampleAutoplaying" class="carousel slide carousel-fade" data-bs-ride="carousel">
                <div class="carousel-inner">
                    <div class="carousel-item active">
                        <img src="storage/imagenescarrusel/perros.jpg" class="d-block w-100" alt="...">
                    </div>
                    <div class="carousel-item">
                        <img src="storage/imagenescarrusel/gatos.jpg" class="d-block w-100" alt="...">
                    </div>
                </div>
                <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleAutoplaying" data-bs-slide="prev">
                    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                    <span class="visually-hidden">Previous</span>
                </button>
                <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleAutoplaying" data-bs-slide="next">
                    <span class="carousel-control-next-icon" aria-hidden="true"></span>
                    <span class="visually-hidden">Next</span>
                </button>
            </div>
        </div>
    </div>
</template>

<style>
.carousel-inner img {
    width: 150%;
    height: 500px; /* Ajusta según tus necesidades */
    object-fit: cover; /* Mantiene la proporción */
}

.carousel {
    max-width: 1000px; /* Ancho máximo del carrusel */
    margin: auto; /* Centrado */
}
</style>

<script>
import 'bootstrap';
import 'bootstrap/dist/css/bootstrap.min.css';

export default {
    data: function() {
        return {
          
        }
    },
    
}

</script>