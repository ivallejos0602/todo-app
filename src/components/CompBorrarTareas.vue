<template lang="">
    <div>
       
        <button @click="borrarTodasLasTareas">borrar TODAS las Tareas</button>
        
    </div>
</template>
<script>
export default {
    data(){
        return {
            idTareaInputBorrar:''
        }
    },
    methods:{
         borrarTodasLasTareas(){
             this.$emit('borrarTodasLasTareasDesdeHijo');
         }

    }

    
}
</script>
<style lang="">
    
</style>