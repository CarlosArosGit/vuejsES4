<template>
    <div class="componenteSesion4">
        <h2>Componente Sesión 4</h2>
        <div id="contenedorPadre">
            <div id="contenedorIzquierda">
                <div class="divImagenes" v-for="(imagen, index) in imagenes">
                    <img class="contenedorImagenes" v-bind:src="imagen" v-bind:alt="index" v-on:click="describirImagen">
                </div>

            </div>
            <div v-if="hayClick" id="contenedorDerecha">
                <div id="contenedorPadreDescripcion">
                    <div id="descripcionIzquierda">
                        <img class="contenedorImagenSeleccionada" v-bind:src="imagenSeleccionada"
                            v-bind:alt="descripcionSeleccionada"><br>
                        <button v-on:click="cerrarDescripcion">Cerrar</button>
                    </div>
                    <div id="descripcionDerecha">
                        <p>{{ descripcionSeleccionada }}</p>
                        <p>{{ autorSeleccionado }}</p>
                    </div>
                </div>


            </div>
        </div>
    </div>
</template>
  
<script>
export default{
    name:'ComponenteSesion4',
    props:{
        imagenes:{
            type:Array,
            required: true,
        },
        descripciones:{
            type: Array,
        },
        autores:{
            type:Array,
        }
    },
    data:function(){
        return{
            hayClick:false,
            imagenSeleccionada:'',
            descripcionSeleccionada:'',
            autorSeleccionado:'',
        }
    },
    methods:{
        describirImagen: function(event){
            this.hayClick = true;
            let indiceDeLaImagen= Number(event.target.alt);
            this.imagenSeleccionada = this.imagenes[indiceDeLaImagen];
            this.descripcionSeleccionada = this.descripciones[indiceDeLaImagen];
            this.autorSeleccionado = this.autores[indiceDeLaImagen];
        },
        cerrarDescripcion: function(){
            this.imagenSeleccionada = '';
            this.descripcionSeleccionada='',
            this.autorSeleccionado='',
            this.hayClick = false;
        },

    }
}
</script>


<style scoped>
#contenedorIzquierda{
    width: 59%;
    display: inline-block;
}

#contenedorDerecha{
    width: 39%;
    display: inline-block;
}

.contenedorImagenes{
    width: 50%;
}

#descripcionIzquierda{
    width:69%;
    display: inline-block;
}

#descripcionDerecha{
    width:29%;
    display: inline-block;
}

.contenedorImagenSeleccionada{
    width:60%;
}


</style>