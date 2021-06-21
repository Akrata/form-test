<template>
  <h2>Editar Tarea</h2>
  <form @submit.prevent="updateTarea(tarea)">
    <InputForm :tarea="tarea"></InputForm>
  </form>
</template>

<script>
import { mapActions, mapState } from 'vuex'
import InputForm from '../components/InputForm.vue'

export default {
    name:'EditarTarea',
    components:{
      InputForm
    },
    computed:{
      ...mapState(['tarea'])
    },
    methods:{
      ...mapActions(['setTarea','updateTarea'])
    },
    created(){
      this.setTarea(this.$route.params.id)
    }
   
}
</script>

<style>

</style>