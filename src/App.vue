<template>
  <div id="app">
     
   <CompAgregarTarea  @agregarNuevaTarea="agregarTarea" ></CompAgregarTarea>
   <CompListarTareas @borrarTareaDesdeHijo="borrarTarea" v-bind:tasks="tareas"></CompListarTareas>
   <CompBorrarTarea @borrarTareaDesdeHijo="borrarTarea"></CompBorrarTarea>
   
  </div>
</template>

<script>

import CompAgregarTarea from './components/CompAgregarTarea'
import CompListarTareas from './components/CompListarTareas'
import CompBorrarTarea from './components/CompBorrarTarea'

export default {
  name: 'App',
  components: {
   CompAgregarTarea,
   CompListarTareas,
   CompBorrarTarea
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
    },
    borrarTarea(numTarea){
           this.tareas = this.tareas.filter(elem => {
                return  (elem.idTarea) !== parseInt(numTarea);
           })

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
