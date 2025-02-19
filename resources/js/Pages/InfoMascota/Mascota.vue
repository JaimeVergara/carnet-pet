<template>
    <div class="container mt-5">
        <div class="row">
            <div class="col text-center texto-blue-alemana">
                <h3>Mis Mascotas</h3>
            </div>
            <div class="d-flex justify-content-end mr-4">
                <button type="button" class="btn btn-dark" v-on:click.prevent="modal_agregar()"><i class="fa-regular fa-address-book"></i></button>
            </div>
        </div>
        <div class="row mt-3">
            <div class="col">
                <table class="table table-striped">
                    <thead>
                        <tr>
                            <th scope="col">ID</th>
                            <th class="no-sort" scope="col">NOMBRE</th>
                            <th class="no-sort" scope="col">ESPECIE</th> 
                            <th class="no-sort" scope="col">RAZA</th>
                            <th class="no-sort" scope="col">INFORMACION</th>
                            <th class="no-sort" scope="col">EDITAR</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>1</td>
                            <td>Canela</td>
                            <td>Perro</td>
                            <td>Mestizo</td>
                            <td>
                                <button type="button" class="btn btn-sm btn-dark" v-on:click.prevent="modal_masinfo()"><i class="fa-solid fa-circle-info"></i> Info</button>
                            </td>
                            <td>
                                <button type="button" class="btn btn-sm btn-dark" v-on:click.prevent="modal_editarinfo()"><i class="fa-solid fa-pen-to-square"></i></button>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
    <ModalAgregar :hash="hash_agregar" />
    <ModalMasInfo :hash="hash_masinfo" />
    <ModalEditarInfo :hash="hash_editar" />
</template>

<style>

</style>

<script>
import 'bootstrap';
import 'bootstrap/dist/css/bootstrap.min.css';
import Toastify from 'toastify-js'
import ModalAgregar from './ModalAgregar.vue';
import ModalMasInfo from './ModalMasInfo.vue';
import ModalEditarInfo from './ModalEditarInfo.vue';

export default {
    components: {
        ModalAgregar,
        ModalMasInfo,
        ModalEditarInfo
    },
    data: function() {
        return {
            hash_agregar: 0,
            hash_masinfo: 0,
            hash_editar: 0,
            datos_tabla: '',
            modificar_page: 0
        }
    },
    methods: {
        modal_agregar(){
            this.hash_agregar = Math.floor(Math.random() * 10001);
        },
        modal_masinfo(){
            this.hash_masinfo = Math.floor(Math.random() * 10001);
        },
        modal_editarinfo(){
            this.hash_editar = Math.floor(Math.random() * 10001);
        },
    }
}

</script>