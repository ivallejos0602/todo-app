<template>
  <div id="app">
     
   <CompAgregarTarea  @agregarNuevaTarea="agregarTarea" ></CompAgregarTarea>

   <CompListarTareas @borrarTareaDesdeHijo="borrarTarea" 
                     @finalizarTareaDesdeHijo="finalizarTarea" 
                     v-bind:tasks="tareas">
    </CompListarTareas>

   <CompBorrarTarea @borrarTareaDesdeHijo="borrarTarea"></CompBorrarTarea>

   <CompBorrarTareas @borrarTodasLasTareasDesdeHijo="borrarTodasLasTareas"></CompBorrarTareas>
   
  </div>
</template>

<script>

import CompAgregarTarea from './components/CompAgregarTarea'
import CompListarTareas from './components/CompListarTareas'
import CompBorrarTarea from './components/CompBorrarTarea'
import CompBorrarTareas from './components/CompBorrarTareas'

export default {
  name: 'App',
  components: {
   CompAgregarTarea,
   CompListarTareas,
   CompBorrarTarea,
   CompBorrarTareas,
  },
  data(){
    return{
         nombreTareaInput:'escriba...',
         idTarea:1,
         tareas:[],
         
         }
    },
  methods: {
    agregarTarea(nombreTareaInput){

        this.tareas.push({
          idTarea: this.idTarea,
          nombreTarea: nombreTareaInput,
          checked:false,
          });
        this.idTarea++;
    },
    borrarTarea(numTarea){
           this.tareas = this.tareas.filter(elem => {
                return  (elem.idTarea) !== parseInt(numTarea);
           })

    },
    finalizarTarea(id){
      console.log("finalizó la tarea"+id);
      this.tareas = this.tareas.map(
                   elem => {
                     if (elem.idTarea === id){
                       elem.checked = !elem.checked;
                     }
                    return elem; 
                   })
     },
     borrarTodasLasTareas(){
          this.tareas=[];
     },
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
