<template lang="">
       <div>
            <ul>
                 <p>me ves git? lalala jajaja!---para ver cambios en la nube</p>
                 <p>nombre tarea</p>
                 <input v-model="nombreTareaInput"/>
                  <p>tiempo tarea</p>
                 <input v-model="tiempoTareaInput"/>
                 
                 <button @click="agregarTarea">agregar Tarea</button>
                 
                 <p>------------------------------</p>
                 <h1>Listado de tareas</h1>
                 <li v-for="tarea in tareas" v-bind:key="tarea.keyTarea">
                      Id Tarea: {{ tarea.keyTarea }} Nombre: {{ tarea.nombre }}, tiempo: {{ tarea.tiempo}} 
                      <button @click="eliminarTareaByButton(tarea.keyTarea)">borrar Tarea {{tarea.keyTarea}}</button> 
                 </li> 
                 <p>------------------------------</p>
                 <p>Eliminar tarea: (Ingrese el Id)</p>
                 <input v-model="idTareaABorrar"/>
                 <button @click="eliminarTarea">borrar Tarea</button>
                 <div>  
                      <br><br>    
                     <button @click="eliminarAllTask">borrar TODAS las Tareas</button>    
                 </div>         

            </ul>
            
         </div>
    </template>
    
<script>
export default {
data()
       {
        return { 
           idTareaABorrar:'',  
           nombreTareaInput:'',
           tiempoTareaInput:'',
           keyTarea:6,
           tareas: [
                {keyTarea:1,nombre:"lavar ropa",tiempo:25},
                {keyTarea:2,nombre:"lavar platos",tiempo:15},
                {keyTarea:3,nombre:"cocinar",tiempo:30},
                {keyTarea:4,nombre:"limpiar piso",tiempo:14},
                {keyTarea:5,nombre:"planchar ropa",tiempo:45},
          ],
        }  
      },
 methods: {
      agregarTarea(){
             
            this.tareas.push({
                 keyTarea:this.keyTarea,
                 nombre: this.nombreTareaInput,
                 tiempo:this.tiempoTareaInput,
                 
               });

            this.keyTarea++;   
      },

      eliminarTarea(){
            
           this.tareas = this.tareas.filter(elem => {
                return  (elem.keyTarea) !== parseInt(this.idTareaABorrar);
           })
      },

      eliminarTareaByButton(idTask){

this.tareas = this.tareas.filter(elem => {
                return  (elem.keyTarea) !== parseInt(idTask);
           })

      },

      eliminarAllTask(){
           this.tareas=[];
      }
 }     
    
}
</script>
<style lang="">
    
</style>