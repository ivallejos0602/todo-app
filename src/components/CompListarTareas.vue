<template lang="">
    <div>
        <p>Listado de tareas desde el comp. CompListarTareas</p>
        <ul>
            
             <li v-for="task in tasks" v-bind:key="task.idTarea" :class="{}" >
                 Id Tarea: {{task.idTarea}}
                 <span :class="{done: task.checked}"> Nombre: {{ task.nombreTarea }}</span>
                 <button @click="borrarTareaById(task.idTarea)">borrar Tarea {{task.idTarea}}</button> 
                 <button @click="terminarTarea(task.idTarea)"> {{!task.checked ? 'Finalizar': 'Reanudar'}} </button>
                    
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
       terminarTarea(arg1){
           this.$emit('finalizarTareaDesdeHijo',arg1);
       }  

      },
  }    

</script>
<style lang="css">
 .done {
        text-decoration:line-through;
    }
    
</style>
