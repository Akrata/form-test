<template>

  <h1 class="my-5">Formularios con Vue.js</h1>

  <form @submit.prevent="procesarFormulario">
    <InputForm :tarea="tarea"></InputForm>
    
  </form>
  <hr>
  <p>
    {{tarea}}
  </p>
  <hr>
  <ListaTareas></ListaTareas>
</template>

<script>
import InputForm from '../components/InputForm.vue'
import ListaTareas from '../components/ListaTareas.vue'
import {mapActions} from 'vuex'
const shortid = require('shortid')

export default {
  name: 'Home',
  components: {
    InputForm,
    ListaTareas,
  },
  data() {
    return {
      tarea: {
        id:'',
        nombre: '',
        categorias: [],
        estado: '',
        numero: 0
      }
    }
  },
  methods: {
    ...mapActions(['setTareas']),
    procesarFormulario(){
      console.log(this.tarea)
      if(this.tarea.nombre.trim() === ""){
        console.log('Campo vacío')
        return
      }
      console.log('no está vacio')
      //generar id
      this.tarea.id = shortid.generate()
      console.log(this.tarea.id);
      this.setTareas(this.tarea)

      
      // envian los datos

      this.tarea = {
        id:'',
        nombre: '',
        categorias: [],
        estado: '',
        numero: 0
      }
    }
  },
  
}
</script>
