<template lang="">
    <div>
        <p>Listado de tareas desde el comp. CompListarTareas</p>
        <ul>
             <li v-for="task in tasks" v-bind:key="task.idTarea">
                      Id Tarea: {{ task.idTarea }} Nombre: {{ task.nombreTarea }} 
                     <button @click="borrarTareaById(task.idTarea)">borrar Tarea {{task.idTarea}}</button> 
             </li>   
        </ul>
    </div>
</template>
<script>
export default {
  props:{
      tasks:Array,
  },
  methods:{
      borrarTareaById(arg){
          console.log("borrando:"+arg);
            this.$emit('borrarTareaDesdeHijo',arg);
         },

      },
  }    

</script>
<style lang="">
    
</style>
