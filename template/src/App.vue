<template>
  <div id="app">
    <h1>\{{ msg }}</h1>
    <h2>Here's a map</h2>
    <div id="mapid"></div>
  </div>
</template>


<script>
export default {

  name: 'app',

  data () {
    return {
      msg: 'Welcome to Your Vue.js App that uses Leaflet!',
      map: null,
    }
  },

  mounted() {

    this.map = L.map('mapid').setView([55.710431, 13.208485], 13);

    L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', {
      maxZoom: 18,
      attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, ' +
        '<a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
        'Imagery © <a href="http://mapbox.com">Mapbox</a>',
      id: 'mapbox.streets'
    }).addTo(this.map);

    var marker = L.marker([55.710431, 13.208485]).addTo(this.map);

  }
}
</script>

<style{{#sass}} lang="scss"{{/sass}}>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

#mapid { 
  height: 500px; 
}
</style>
