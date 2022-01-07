<template>
  Editar {{ $route.params.id }} - {{tarea}}
  <form class="container" @submit.prevent="updateTarea(tarea)">
    <Imputs :dato="tarea" />
  </form>
</template>

<script>
import  {mapState, mapActions} from 'vuex'
import Imputs from '../components/Inputs.vue'
export default {
    components:{
        Imputs
    },
    computed:{
        ...mapState(['tarea'])
    },
    methods: {
        ...mapActions(['setTarea', 'updateTarea'])
    },
    created() {
        this.setTarea(this.$route.params.id)
    },
}
</script>

<style>

</style>