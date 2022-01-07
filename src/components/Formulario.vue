<template>
  <form class="container" @submit.prevent="Guardar()">
      <Form :dato="datos" />
  </form>
  <hr>
    <Table :dato="datos" />
  {{this.datos}}
</template>

<script>
import Form from '../components/Inputs.vue'
import Table from '../components/Table.vue'
import {mapActions} from 'vuex'
const shortid = require('shortid');

export default {
    components:{
        Form,
        Table
    },
    data() {
        return {
            datos:{
                id:'',
                nombre: '',
                categoria: [],
                estado: '',
                numero: 0
            }
        }
    },
    methods: {
        ...mapActions(['setTareas']),
        Guardar(){
            if(this.datos.nombre.trim() === ""){
                console.log("Campo Vacio");
                return;
            }   
            console.log('No esta vacio');
            this.datos.id = shortid.generate();
            console.log(this.datos);
            this.setTareas(this.datos);
            this.datos = {
                id:'',
                nombre: '',
                tipo: [],
                preoridad: '',
                numero: 0
            }
        },  
    }

}
</script>