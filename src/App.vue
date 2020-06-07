<template>
  <div id="app">
    <div class="caja">
      <h1>Random Gif Cat</h1>Titulo
      <input type="text" v-model="titulo">
      <br>Filtros
      <select type="text" v-model="filtro">
        <option value="blur">blur</option>
        <option value="mono">mono</option>
        <option value="sepia">sepia</option>
        <option value="negative">negative</option>
        <option value="paint">paint</option>
        <option value="pixel">pixel</option>
      </select>
      <br>Color
      <select type="text" v-model="color">
        <option value="blue">blue</option>
        <option value="yellow">yellow</option>
        <option value="green">green</option>
        <option value="grey">grey</option>
        <option value="red">red</option>
        <option value="black">black</option>
      </select>
      <br>Tamaño
      <input type="text" v-model="tamaño"> px
      </div>
     <button @click="src">Obtén tu Gatito</button
           <img :src="src">
     
    </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      titulo: "",
      filtro: "",
      color: "",
      tamaño: "",
    };
  },
  computed: {
    src() {
      let titulo = this.titulo;
      let color = this.color;
      let filtro = this.filtro;
      let tamaño = this.tamaño;
      return `https://cataas.com/cat/gif/says/${titulo}?filter=${filtro}&color=${color}&size=${tamaño}`;
    }
  }
};
</script>

<style>
.caja{
  background-color: #f08080
}
#app {
  padding-top: 3rem; 
  padding-bottom: 3rem;
  background-color: #add8e6 ;
  display: flex,
}
button{
  display: flex center;
}
h1{
  text-align: center; 
}

</style>
