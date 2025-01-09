<template>
    <div class="container">
        <div class="formulario">
            <div class="foto">
                <label for="">Fotograf&#237;a</label>
                <img :src="candidatos.foto " alt="Cargando...">
               
            
            </div>
            <div class="datos">
                <p type="T&#237;tulo">
                <p class="dato">{{ candidatos.titulo }}</p></p>
            
               
                <p type="Nombre">
                    <p class="dato">{{ candidatos.nombre }}</p>
            </p>
                <p type="Apellido">
                    <p class="dato">{{ candidatos.apellido }}</p>
            </p>
                <p type="Correo">
                    <p class="dato">{{ candidatos.atributo5 }}</p>
            </p>
                <p type="Tel&#233;fono">
                    <p class="dato">{{ candidatos.atributo6 }}</p>
            </p>
            </div>

            <div class="botones">
                <button class="buscar" @click="buscar">Buscar</button>
                <button class="agregar">Agregar</button>
                <Agregar v-show="mostrar" @candidatos="candidatos"></Agregar>
            </div>
        </div>
    </div>

</template>
<script>
import Agregar from '@/components/AgregarCandidatos.vue'
export default {
    components: {
        Agregar
    },
    data() {
        return {
            candidatos: {
                titulo: "",
                foto: "",
                nombre: "",
                apellido: "",
                atributo5: "",
                atributo6: ""
            }
            ,
            mostrar:false
        }
    },
    methods: {
        async llamarApi() {
            const data = await fetch('https://randomuser.me/api/').then(response => response.json())

            const candidato = data.results[0];
            this.candidatos = {
                titulo: candidato.name.title,
                foto: candidato.picture.large,
                nombre: candidato.name.first,
                apellido: candidato.name.last,
                atributo5: candidato.email,
                atributo6: candidato.phone
            }
        },
        buscar() {
            this.llamarApi();
        }
    },

   
}
</script>

<style scoped>
#lb {
    border: solid 1px black;

}

.container {
    display: flex;
    justify-content: center;
    align-content: center;
    align-items: center;
   

}

.formulario {
    width: 250px;
    border: 1px solid blue;
    padding: 10px;
    border-radius: 35px;

}

p::before {
    display: block;
    content: attr(type);
    font-weight: bold;
    font-size: 20px;
    color: blue;

}



.foto {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: row;

}

.foto input {
    width: 100px;
    height: 100px;
    border: 1px solid blue;
    border-radius: 1px;
    margin-left: 15px;
}
 .dato{
    border:solid 1px black;
    height: 20px;
}

p{
    display: block;
   
}

.foto img{
    border:solid 1px blue;
    border-radius: 15px;
    height: 100px;
    width: 100px;
    margin-left: 15px;
}

label{
    font-weight: bold;
    font-size: 20px;
    color: blue;
}
button{
    width:70px;
    height: 30px;
    font-size: 17px;
    background-color: blue;
    border: solid 1px white;
    color: white;
    border-radius: 10px;

}
.agregar,.buscar{
    margin: 10px;
}
</style>