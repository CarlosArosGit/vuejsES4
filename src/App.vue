<template>
  <div id="app">
    <ComponenteSesion4 
    v-bind:imagenes="arregloImagenes"
    v-bind:descripciones="arregloDescripciones"
    v-bind:autores="arregloAutores"
    />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ComponenteSesion4 from './components/ComponenteSesion4.vue'
export default {
  name: 'App',
  components: {
    ComponenteSesion4
  },
  data:function(){
    return{
      arregloImagenes:[
        'https://cdn.pixabay.com/photo/2016/02/10/21/59/landscape-1192669_640.jpg',
        'https://www.dzoom.org.es/wp-content/uploads/2017/07/seebensee-2384369-810x540.jpg',
        'https://www.10wallpaper.com/wallpaper/medium/2104/Norway_lofoten_mountains_2021_Scenery_5K_Photo_medium.jpg'
      ],
      arregloDescripciones:[
        'PAISAJE 1',
        'PAISAJE 2',
        'PAISAJE 3'
      ],
      arregloAutores:[
        'AUTOR 1',
        'AUTOR 2',
        'AUTOR 3',
      ],
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
