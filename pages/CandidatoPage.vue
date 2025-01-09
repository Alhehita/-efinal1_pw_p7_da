<template>
    <div class="componentes">
        <Buscar></Buscar>
        <Agregar></Agregar>

    </div>
  
</template>

<script>
import Agregar from '@/components/AgregarCandidatos.vue'
import Buscar from '@/components/BuscarCandidatos.vue'
export default {

    components: {
        Agregar,
        Buscar
    }

}
</script>

<style scoped>
.componentes {
    display: flex;
    justify-content: center;
    align-content: center;
    align-items: center;
    flex-direction: column;

}

</style>