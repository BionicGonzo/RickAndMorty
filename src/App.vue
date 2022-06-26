<template>
  <div id="app" class="rickandmorty min-vh-100 p-5 text-center">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <div class="d-inline-flex p-3">
      <h1 class="text-light">Rick and Morty</h1>
    </div>
    <Personaje :data="listaPersonajes"/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Personaje from "@/components/Personaje";

export default {
  name: 'app',
  components: {
    Personaje
  },
  data(){
    return {
      listaPersonajes: []
    }
  },
  methods: {
    async llamarPersonajes(){
      try {
        const data = await fetch('https://rickandmortyapi.com/api/character')
        const personajes = await data.json()
        this.listaPersonajes = personajes.results
        console.log(this.listaPersonajes)
      } catch (error) {
        console.warn(error)
      }
    }
  },
  created() { // al crear la instancia se llama a la función
    this.llamarPersonajes()
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
  /* margin-top: 60px; */
}

.rickandmorty {
  background-image: url("https://rickandmortypod.com/wp-content/uploads/2018/11/cropped-RM_page-header_background1-3.png");
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
}
</style>
