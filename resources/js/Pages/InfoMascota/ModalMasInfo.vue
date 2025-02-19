<template>
    <div class="modal fade" id="modalMasInfo" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="exampleModalLabel">Más Información de Canela</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body">
                    <ul class="list-unstyled text-start">
                        <li>Color: Blanco/cafe</li>
                        <li>Sexo: Hembra</li>
                        <li>Cumpleaños: 15 de marzo de 2020</li>
                        <li>Numero de Chip: 1111111111119</li>
                    </ul>
                    <span><strong>Información Familiar</strong></span>
                    <ul class="list-unstyled text-start">
                        <li>Persona Responsable: Jaime Vergara</li>
                        <li>Direccion: Ayquina 142</li>
                        <li>Ciudad: Valdivia</li>
                        <li>Telefono: 123456789</li>
                        <li>Correo: jaime@vergara</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import 'bootstrap';
import 'bootstrap/dist/css/bootstrap.min.css';
import { Modal } from 'bootstrap';

export default {
    props: ['hash'],
    data: function() {
        return {
            modal_info: ''
        }
    },
    watch: {
        hash: function(){
            this.modal_info.show();
        }
    },
    mounted() {
        this.modal_info = new Modal(document.getElementById('modalMasInfo'));
    }
}
</script>