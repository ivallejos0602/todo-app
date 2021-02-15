<template lang="">
    <div>
        <p>Ingrese el id de la tarea a borrar:</p>
        <input v-model="idTareaInputBorrar"/>
        <button @click="borrarTareaById">borrar Tarea</button>
        
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
         borrarTareaById(){
             this.$emit('borrarTareaDesdeHijo',this.idTareaInputBorrar);
         }

    }

    
}
</script>
<style lang="">
    
</style>