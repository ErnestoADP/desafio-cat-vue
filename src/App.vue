<template>
  <div id="app">
    <h1>Random Gift Cat</h1>
    <section class="gato">
      <form >
        <div><label>Título:</label>
          <input type="text" class="form-control" v-model="titulo">
        </div>
        <div class="form-group">
          <label>Filtro:</label>
          <select class="form-control" v-model="filtro">
            <option value="blur">Blur</option>
            <option value="mono">Mono</option>
            <option value="negative">Negative</option>
            <option value="paint">Paint</option>
            <option value="pixel">Pixel</option>
            <option value="sepia">Sepia</option>
          </select>
        </div>
        <div>
          <label>Color:</label>
          <select class="form-control" v-model="color">
            <option value="yellow">Amarillo</option>
            <option value="blue">Azúl</option>
            <option value="purple">Morado</option>
            <option value="orange">Naranjo</option>
            <option value="red">Rojo</option>
            <option value="green">Verde</option>
          </select>
        </div>
        <div>
          <label>Tamaño:</label>
          <input type="text" class="form-control" v-model="tamano" @keyup.enter="showImage">
        </div>
      </form>
    </section>
    <button type="button" class="btn btn-success" @click="showImage">Obtener mi gatito</button>
    <section id="image">
      <div class="">
        <img :src="urlImage" alt="">
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      title: 'Random Gif Cat',
      urlImage: null,
      titulo: null,
      color: null,
      filtro: null,
      tamano: null
    }
  },
  methods: {
    showImage() {
      this.urlImage = `https://cataas.com/cat/gif/says/${this.titulo}?filter=${this.filtro}&color=${this.color}&size=${this.tamano}`;
      console.log('url', this.urlImage);
    }
  }
}
</script>

<style>
body {
  padding:0;
  margin:0;
  background-color: rgb(134, 221, 255);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}

.image {
  height: auto;
}

.gato {
  background-color: #ff847c;
  padding: 20px;
  width: 100%;
  height: auto;

}

.btn {
margin: 20px;
}

.form-control {
margin-top: 20px;
}

</style>