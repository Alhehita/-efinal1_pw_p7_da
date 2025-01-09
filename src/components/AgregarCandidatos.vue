<template>
  <div class="container">
    <div class="tabla">
        <table>
            <thead>
                <tr>
                    <th>T&#237;tulo</th>
                    <th>Nombre</th>
                    <th>Apellido</th>
                    <th>Correo</th>
                    <th>Tel&#233;fono</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="candidato in candidatos" :key="candidato">
                    <td>{{candidato.titulo}}</td>
                    <td>{{candidato.nombre}}</td>
                    <td>{{candidato.apellido}}</td>
                    <td>{{candidato.correo}}</td>
                    <td>{{candidato.telefono}}</td>
                  
                </tr>
            </tbody>
        </table>
    <div></div>
    </div>
  </div>
</template>

<script>
export default {

    props:{
        candidatos:{
            type: Array,
            required: false
        }
    }
}
</script>

<style scoped>

th, tr{
    border: 1px solid black;
    padding: 10px;  
}



</style>