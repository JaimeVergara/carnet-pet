<template>
    <div class="modal fade" id="agregarModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog modal-dialog-centered modal-dialog-scrollable modal-lg">
        <div class="modal-content">
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="exampleModalLabel">Agregar una nueva Mascota</h1>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            <form>
              <div class="mb-3">
                <label for="nombreMascota" class="form-label">Nombre de la Mascota:</label>
                <input type="text" class="form-control" id="nombreMascota" placeholder="Ingrese el nombre de la mascota">
              </div>
              <div class="mb-3">
                <label for="apellidoMascota" class="form-label">Apellido de la Mascota:</label>
                <input type="text" class="form-control" id="apellidoMascota" placeholder="Ingrese el apellido de la mascota">
              </div>
            </form>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-sm btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="button" class="btn btn-sm btn-primary">Save changes</button>
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
            modal_agregar: ''
        }
    },
    watch: {
        hash: function(){
            this.modal_agregar.show();
        }
    },
    mounted() {
        this.modal_agregar = new Modal(document.getElementById('agregarModal'));
    }
}
</script>