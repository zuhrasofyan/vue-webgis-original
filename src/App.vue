<template>
  <div class="">
    <Navbar></Navbar>
    <div id="map">
      <v-map :zoom="zoom" :center="center">
        <v-tilelayer :url="url" :attribution="attribution"></v-tilelayer>
        <v-marker :lat-lng="marker"></v-marker>
      </v-map>
    </div>
    <div class="row">
      <div class="col-sm">
        <div class="alert alert-primary" role="alert">
          This is a primary alert—check it out!
        </div>
        One of three columns
        <b-button variant="success" v-b-modal.modal-center>Succes!</b-button>
        <b-btn variant="success">Succes!</b-btn>
      </div>
      <div class="col-sm">
        One of three columns
      </div>
      <div class="col-sm">
        One of three columns
      </div>
    </div>
    <!-- Modal Component -->
    <b-modal id="modal-center" centered title="Bootstrap-Vue">
      <p class="my-4">Hello from modal!</p>
    </b-modal>
    <router-view></router-view>
  </div>
</template>

<script>
import Navbar from './components/Navbar'

export default {
  name: 'app',
  components: {
    Navbar
  },
  data () {
    return {
      zoom: 13,
      center: [47.413220, -1.219482],
      url: 'http://{s}.tile.osm.org/{z}/{x}/{y}.png',
      attribution: '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      // eslint-disable-next-line
      marker: L.latLng(47.413220, -1.219482)
    }
  }
}
</script>

<style>
#map {
  height: 300px;
}
</style>
