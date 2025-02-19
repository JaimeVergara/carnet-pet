<template>
    <AppLayout title="Dashboard">
       <div class="container-fluid">
            <div class="row justify-content-center">
                <div class="col-6">
                    <ul class="nav nav-tabs justify-content-center">
                        <li class="nav-item">
                            <a type="button" :class="isInicioActiveM ? 'nav-link active texto-negro' : 'nav-link texto-negro'" v-on:click.prevent="press_mascota()">Mis Mascotas</a>
                        </li>
                        <li class="nav-item">
                            <a type="button" :class="isInicioActiveV ? 'nav-link active texto-negro' : 'nav-link texto-negro'" v-on:click.prevent="press_vacunacion()">Vacunación</a>
                        </li>
                        <li class="nav-item">
                            <a type="button" :class="isInicioActiveD ? 'nav-link active texto-negro' : 'nav-link texto-negro'" v-on:click.prevent="press_desparacitacion()">Desparacitación</a>
                        </li>
                        <li class="nav-item">
                            <a type="button" :class="isInicioActiveVet ? 'nav-link active texto-negro' : 'nav-link texto-negro'" v-on:click.prevent="press_veterinario()">Veterinario</a>
                        </li>
                        <li class="nav-item">
                            <a type="button" :class="isInicioActiveP ? 'nav-link active texto-negro' : 'nav-link texto-negro'" v-on:click.prevent="press_peluqueria()">Baño y peluqueria</a>
                        </li>
                    </ul>
                </div>
            </div>
       </div>
       <Mascota v-if="mascota_view"/>
       <Vacunacion v-if="vacunacion_view"/>
       <Desparacitacion v-if="desparacitacion_view"/>
       <Veterinario v-if="veterinario_view"/>
       <Peluqueria v-if="peluqueria_view"/>
    </AppLayout>
</template>

<style>
    .texto-negro {
        color: black;
        text-decoration: none; /* Para quitar el subrayado si lo deseas */
    }
    .texto-negro:hover {
        color: gray; /* Color al pasar el cursor (opcional) */
    }
</style>

<script>
import AppLayout from '@/Layouts/AppLayout.vue';
import 'bootstrap';
import 'bootstrap/dist/css/bootstrap.min.css';
import Mascota from './InfoMascota/Mascota.vue';
import Vacunacion from './InfoMascota/Vacunacion.vue';
import Desparacitacion from './InfoMascota/Desparacitacion.vue';
import Veterinario from './InfoMascota/Veterinario.vue';
import Peluqueria from './InfoMascota/Peluqueria.vue';

export default {
    data: function(){
        return {
            isInicioActiveM: false,
            isInicioActiveV: false,
            isInicioActiveD: false,
            isInicioActiveVet: false,
            isInicioActiveP: false,
            mascota_view: false,
            vacunacion_view: false,
            desparacitacion_view: false,
            veterinario_view: false,
            peluqueria_view: false
        }
    },
    components: {
        AppLayout,
        Mascota,
        Vacunacion,
        Desparacitacion,
        Veterinario,
        Peluqueria
    },   
    mounted(){
        this.press_mascota();
    },
    methods: {
        press_mascota(){
            this.isInicioActiveM = true;
            this.isInicioActiveV = false;
            this.isInicioActiveD = false;
            this.isInicioActiveVet = false;
            this.isInicioActiveP = false;
            this.mascota_view = true;
            this.vacunacion_view = false;
            this.desparacitacion_view = false;
            this.veterinario_view = false;
            this.peluqueria_view = false;
        },
        press_vacunacion(){
            this.isInicioActiveM = false;
            this.isInicioActiveV = true;
            this.isInicioActiveD = false;
            this.isInicioActiveVet = false;
            this.isInicioActiveP = false;
            this.mascota_view = false;
            this.vacunacion_view = true;
            this.desparacitacion_view = false;
            this.veterinario_view = false;
            this.peluqueria_view = false;
        },
        press_desparacitacion(){
            this.isInicioActiveM = false;
            this.isInicioActiveV = false;
            this.isInicioActiveD = true;
            this.isInicioActiveVet = false;
            this.isInicioActiveP = false;
            this.mascota_view = false;
            this.vacunacion_view = false;
            this.desparacitacion_view = true;
            this.veterinario_view = false;
            this.peluqueria_view = false;
        },
        press_veterinario(){
            this.isInicioActiveM = false;
            this.isInicioActiveV = false;
            this.isInicioActiveD = false;
            this.isInicioActiveVet = true;
            this.isInicioActiveP = false;
            this.mascota_view = false;
            this.vacunacion_view = false;
            this.desparacitacion_view = false;
            this.veterinario_view = true;
            this.peluqueria_view = false;
        },
        press_peluqueria(){
            this.isInicioActiveM = false;
            this.isInicioActiveV = false;
            this.isInicioActiveD = false;
            this.isInicioActiveVet = false;
            this.isInicioActiveP = true;
            this.mascota_view = false;
            this.vacunacion_view = false;
            this.desparacitacion_view = false;
            this.veterinario_view = false;
            this.peluqueria_view = true;
        }
    }
};
</script>


