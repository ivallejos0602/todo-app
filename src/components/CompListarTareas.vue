<template lang="">
    <div>
        <p>Listado de tareas desde el comp. CompListarTareas</p>
        <ul>
             <li v-for="task in tasks" v-bind:key="task.idTarea">
                      Id Tarea: {{ task.idTarea }} Nombre: {{ task.nombreTarea }} 
                     <button @click="eliminarTareaByButton(task.idTarea)">borrar Tarea {{task.idTarea}}</button> 
             </li>   
        </ul>
    </div>
</template>
<script>
export default {
  props:{
      tasks:Array,
  }    
}
</script>
<style lang="">
    
</style>
