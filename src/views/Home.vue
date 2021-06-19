<template>
  <Formulario :tarea="tarea"></Formulario>
  <hr>
  <p>{{tarea}}</p>
</template>

<script>
// @ is an alias to /src
import Formulario from '../components/Formulario.vue'

export default {
  name: 'Home',
      data() {
    return {
     tarea:{
       nombre: '',
       categorias: [],
       urgente: '',
       numero:'',
       estadoBoton: true
     }
    }
  },
  components: {
    Formulario,
  },
  
}
</script>
