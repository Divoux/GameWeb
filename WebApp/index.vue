<template>
  <div class="container">
    <div>
      <li v-for="(land, index) in lands" :key="index"><NuxtLink :to="`land/${index}`">{{land.post_title}}</NuxtLink></li>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'homepage',
  data(){
    return{
      lands: [],
    }
  },
  mounted(){
    axios.get("http://www.ddivoux.mmi.o2switch.site/wp-json/wp/v2/monstre").then(response => this.lands = response.data);
  }
}
</script>

<style>

.logo {
  max-width: 300px;
}

.o-button {
  padding: 10px 30px;
}

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  flex-direction: column;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.buttons {
  padding-top: 15px;
}
</style>
