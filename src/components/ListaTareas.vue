<template>
  <table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Nombre</th>
      <th scope="col">Categorias</th>
      <th scope="col">Estado</th>
      <th scope="col">Numero</th>
      <th scope="col">Accion</th>
    </tr>
  </thead>
  <tbody>
      <tr v-for="item in tareas" :key="item.id">  
        
        <th>{{item.id}}</th>
        <td>{{item.nombre}}</td>
        <td>
            <!-- <span v-for="(cat, index) in item.categorias" :key="index">
                {{(item.categorias.length === index +1) ? cat : cat + ', '}}
            </span> -->
            <span>
                {{item.categorias.join(', ')}}
            </span>
        </td>
        <td>{{item.estado}}</td>
        <td>{{item.numero}}</td>
        <td>
            <router-link :to="{name:'Editar', params:{id:item.id}}" class="btn btn-warning btn-sm ml-2">Editar</router-link>
            <button class="btn btn-danger btn-sm" @click="borrarTarea(item.id)">Eliminar</button>  
        </td>
        
      </tr>
    <div v-for="item in items" :key="item.id">
        {{ item }}
    </div>
  
  </tbody>
</table>
</template>

<script>
import { mapActions, mapState } from 'vuex'
export default {
    name:'ListaTareas',
    computed:{
        ...mapState(['tareas']),
        
    },
    methods:{
        ...mapActions(['deleteTarea']),
        borrarTarea(item){
            if(confirm("Seguro que desea eliminar?")) {
                 this.deleteTarea(item)
            }
        }
    }

}
</script>

<style>

</style>