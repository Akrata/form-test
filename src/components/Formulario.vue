<template>
  <form @submit.prevent="procesarFormulario">
    <input 
      type="text"
      class="form-control my-2"
      placeholder="Ingrese nombre"
      v-model.trim="tarea.nombre"
    >
    <div class="form-check form-check-inline">
      <input class="form-check-input" id="check1" type="checkbox"  value="Javascript" v-model="tarea.categorias"> 
      <label for="check1" class="form-check-label">
        Javascript
      </label>
    </div>
        <div class="form-check form-check-inline">
      <input class="form-check-input" id="check2" type="checkbox"  value="NodeJS" v-model="tarea.categorias"> 
      <label for="check2" class="form-check-label">
        NodeJs
      </label>
    </div>
        <div class="form-check form-check-inline">
      <input class="form-check-input" id="check3" type="checkbox"  value="PHP" v-model="tarea.categorias"> 
      <label for="check3" class="form-check-label">
        PHP
      </label>
    </div>
    <div class="form-check mt-2">
      <div class="form-check form-check-inline ">
      <input class="form-check-input" id="radio1" type="radio"  value="Urgente" v-model="tarea.urgente"> 
      <label for="radio1" class="form-check-label">
        Urgente
      </label>
      </div>
      <div class="form-check form-check-inline">
      <input class="form-check-input" id="radio1" type="radio"  value="No urgente" v-model="tarea.urgente"> 
      <label for="radio2" class="form-check-label">
        No urgente
      </label>
      </div>
    </div>  
    <div class="mt2">
      <input 
        class="form-control"
        type="number" 
        v-model.number="tarea.numero" >
    </div>
    <button :disabled="deshabilitarBoton" class="btn btn-dark btn-block mt-2 " type="submit">Procesar</button>
  </form>
</template>

<script>
export default {
    props:{
        tarea:Object
    },
  methods:{
    procesarFormulario(){
      console.log(this.tarea);
      if (this.tarea.nombre.trim() === ""){
        console.log("campo vacío");
        return
      }
      console.log("no está vacío");
      console.log(tarea);
      this.limpiarFormulario()
    },
    limpiarFormulario(){
       tarea={
       nombre: '',
       categorias: [],
       urgente: '',
       numero:'',
       estadoBoton: true
     }
    }
  },
  computed:{
    deshabilitarBoton(){
      return this.tarea.nombre.trim() === "" ? true : false
    }
  }

}
</script>

<style>

</style>