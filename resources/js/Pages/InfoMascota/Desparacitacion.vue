<template>
    <div class="container mt-5">
        <div class="row">
            <div class="col text-center texto-blue-alemana">
                <h3>Desparacitación</h3>
            </div>
            <div class="d-flex justify-content-end mr-4">
                <button type="button" class="btn btn-sm btn-primary" v-on:click.prevent="modal_agregar()">Agregar</button>
            </div>
        </div>
        <!-- <div class="row justify-content-end mt-2 mb-2">
            <div class="col-12 text-end fs-5">
                <transition name="fade">
                    <div v-if="loading_data_pac_contactar">
                        <div class="spinner-border spinner-border-sm texto-green-alemana" role="status">
                            <span class="sr-only">Loading...</span>
                        </div>
                        <span class="texto-green-alemana"> Obteniendo Listado Profesionales...</span>
                    </div>
                </transition>
            </div>
        </div> -->
        <div class="row mt-3">
            <div class="col">
                <table id="table-data-arancel" class="table table-striped table-sm">
                    <thead>
                        <tr>
                            <th scope="col">ID</th>
                            <th class="no-sort" scope="col">NOMBRE</th>
                            <th class="no-sort" scope="col">ESPECIE</th> 
                            <th class="no-sort" scope="col">RAZA</th>
                            <th class="no-sort" scope="col">MAS INFORMACION</th>
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
                                
                            </td>
                            <td>
                                
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
import 'datatables.net-bs5'
import 'datatables.net-bs5/js/dataTables.bootstrap5.min'; 
import 'bootstrap/dist/css/bootstrap.min.css'; 
import $ from 'jquery'; 
import { nextTick } from 'vue';

export default {
    components: {
    },
    data: function() {
        return {
        }
    },
    mounted() {
        this.setTable();
    },
    methods: {
        setTable(){
            nextTick(() => {
                this.datos_tabla = $('#table-data-arancel').DataTable({
                    "language": {
                        "lengthMenu": "Mostrar _MENU_",
                        "zeroRecords": "No hay datos encontrados",
                        "info": "Mostrando página _PAGE_ de _PAGES_ de _TOTAL_ registros totales",
                        "infoEmpty": "No hay datos disponibles",
                        "infoFiltered": "(filtrado de _MAX_ registros totales)",
                        "search": "Buscar _INPUT_",
                        // "paginate": {
                        //     "first":      "Primero",
                        //     "last":       "Ultimo",
                        //     "next":       "Siguiente",
                        //     "previous":   "Anterior"
                        // },
                    },
                    "autoWidth": false,
                    "sort": true,
                    "orderable": true,
                    "lengthMenu": [
                        [25, 50, 100, 200],
                        [25, 50, 100, 200]
                    ],
                    "order" : [
                        [0, 'asc']
                    ],
                    "columnDefs": [
                        {
                            "targets": 'no-sort', 
                            "orderable": false
                        }
                    ]
                    // "columnDefs": [
                    //     { "type": "date", "targets": 0 },
                    //     { "orderable": false, "targets": 10 }
                    // ]
                }).page(this.modificar_page).draw(false);
            });
        }
    }
}

</script>