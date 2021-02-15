<template lang="">
    <div>
        <p>Agregar Tarea</p>
       <input v-model="nombreTareaInput"/>
        <button @click="agregarNuevaTarea">agregar Tarea</button>
        
    </div>
</template>
<script>
export default {
   data(){
        return {
            nombreTareaInput:''
        }
   },      
   methods: {
       agregarNuevaTarea(){
           
           this.$emit('agregarNuevaTarea',this.nombreTareaInput);
       }
   },  
}
</script>
<style lang="">
    
</style>
