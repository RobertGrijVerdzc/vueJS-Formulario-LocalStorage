<template>
    <div>
        <input class="form-control form-control-sm" v-model.trim="dato.nombre" type="text">
    </div>
    <div class="mb-3 form-check form-check-inline">
        <input type="checkbox" v-model="dato.categoria" value="JavaScript" class="form-check-input" id="exampleCheck1">
        <label class="form-check-label" for="exampleCheck1">JavaScript</label>
    </div>
    <div class="mb-3 form-check form-check-inline">
        <input type="checkbox" v-model="dato.categoria" value="NnodeJS" class="form-check-input" id="exampleCheck1">
        <label class="form-check-label" for="exampleCheck1">NnodeJS</label>
    </div>  
    <hr>
    <div class="form-check form-check-inline">
        <input class="form-check-input" type="radio" name="inlineRadioOptions" v-model="dato.estado" id="inlineRadio1" value="Alta">
        <label class="form-check-label" for="inlineRadio1">Alta</label>
    </div>
    <div class="form-check form-check-inline">
        <input class="form-check-input" type="radio" name="inlineRadioOptions" v-model="dato.estado" id="inlineRadio2" value="Baja">
        <label class="form-check-label" for="inlineRadio2">Baja</label>
    </div>
    <input type="number" v-model.number="dato.numero" class="form-control form-control-sm">
    <button :disabled="bloquear" type="submit" class="btn btn-red">Guardar</button>
</template>

<script>
export default {
    props:{
        dato: Object
    },
    computed:{
        bloquear(){
            return this.dato.nombre.trim() === "" ? true : false
        }
    }
}
</script>