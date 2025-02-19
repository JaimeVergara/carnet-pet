<template>
    <div class="modal fade" id="modalEditar" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="exampleModalLabel">Editar Información de Canela</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body">
                    
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
            modal_editar: ''
        }
    },
    watch: {
        hash: function(){
            this.modal_editar.show();
        }
    },
    mounted() {
        this.modal_editar = new Modal(document.getElementById('modalEditar'));
    }
}
</script>