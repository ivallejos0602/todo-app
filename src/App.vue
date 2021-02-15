<template>
  <div id="app">
     
   <CompAgregarTarea  @agregarNuevaTarea="agregarTarea" ></CompAgregarTarea>
   <CompListarTareas v-bind:tasks="tareas"></CompListarTareas>
   
  </div>
</template>

<script>

import CompAgregarTarea from './components/CompAgregarTarea'
import CompListarTareas from './components/CompListarTareas'

export default {
  name: 'App',
  components: {
   CompAgregarTarea,
   CompListarTareas
  },
  data(){
    return{
         nombreTareaInput:'escriba...',
         idTarea:1,
         tareas:[]  
         }
    },
  methods: {
    agregarTarea(nombreTareaInput){

        this.tareas.push({
          idTarea: this.idTarea,
          nombreTarea: nombreTareaInput
          });
        this.idTarea++;
    }
  },  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
