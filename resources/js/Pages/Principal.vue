<template>
     <Head title="Inicio" />
     <div class="container-fluid">
        <header>
            <div class="row">
                <div class="d-flex justify-content-center align-items-center esp_logo">
                    <img src="/storage/imagenescarrusel/Logo.jpg" style="width: 15%;" alt="logo">
                </div>
            </div>
        </header>
        <div class="row justify-content-center">
            <div class="col-6">
                <ul class="nav nav-tabs justify-content-center">
                    <li class="nav-item">
                        <a type="button" :class="isInicioActive ? 'nav-link active texto-negro' : 'nav-link texto-negro'" v-on:click.prevent="press_inicio()">Inicio</a>
                    </li>
                    <li class="nav-item">
                        <a type="button" class="nav-link texto-negro" v-on:click.prevent="press_blog()">Blog</a>
                    </li>
                    <li class="nav-item">
                        <a type="button" class="nav-link texto-negro" v-on:click.prevent="press_about()">Quíenes Somos?</a>
                    </li>
                    <li class="nav-item dropdown text-end">
                        <a class="nav-link dropdown-toggle texto-negro" data-bs-toggle="dropdown" href="#" role="button" aria-expanded="false">Ingresar</a>
                        <ul class="dropdown-menu">
                            <li><a class="dropdown-item" :href="route('login')" target="_blank">Iniciar</a></li>
                            <li><a class="dropdown-item" :href="route('register')">Registrar</a></li>
                        </ul>
                    </li>
                </ul>
            </div>
        </div>
       <Inicio v-show="show_ingreso"/>
       <Blog v-show="show_blog"/>
       <About v-show="show_about"/>
       <footer class="text-center mt-4">
            <div class="row">
                <div class="col-12">
                    <a href="https://www.facebook.com" target="_blank"><i class="fa-brands fa-facebook-f fa-2x texto-negro"></i></a> |
                    <a href="https://www.twitter.com" target="_blank"><i class="fa-brands fa-x-twitter fa-2x texto-negro"></i></a> |
                    <a href="https://www.instagram.com" target="_blank"><i class="fa-brands fa-instagram fa-2x texto-negro"></i></a> |
                    <a href="mailto:contacto@ejemplo.com"><i class="fa-regular fa-envelope fa-2x texto-negro"></i></a>
                </div>
                <div class="col-12 mt-2">
                    <p class="text-muted">© 2024 Carnet PET - Todos los derechos reservados</p>
                </div>
            </div>
        </footer>
    </div>
</template>

<style>
.esp_logo{
    height: 40vh;
}
.texto-negro {
    color: black;
    text-decoration: none; /* Para quitar el subrayado si lo deseas */
}
.texto-negro:hover {
    color: gray; /* Color al pasar el cursor (opcional) */
}

</style>

<script>
import 'bootstrap';
import 'bootstrap/dist/css/bootstrap.min.css';
import Inicio from './Inicio.vue';
import Blog from './Blog.vue';
import About from './About.vue';
import { Head } from '@inertiajs/vue3';

export default {
    data: function() {
        return {
            isInicioActive: true,
            show_ingreso: false,
            show_blog: false,
            show_about: false
        }
    },
    components: {
        Inicio,
        Blog,
        About,
        Head
    },
    mounted() {
        this.press_inicio();
    },
    methods: {
        press_inicio() {
            this.isInicioActive = true;
            this.show_ingreso = true;
            this.show_blog = false;
            this.show_about = false;
        },
        press_blog(){
            this.isInicioActive = false;
            this.show_ingreso = false;
            this.show_blog = true;
            this.show_about = false;
        },
        press_about(){
            this.isInicioActive = false;
            this.show_ingreso = false;
            this.show_blog = false;
            this.show_about = true;
        }
    }
}


</script>