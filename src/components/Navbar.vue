<template>
<div>
  <b-navbar toggleable="lg" type="info" variant="light">
    <div class="container">
      <b-navbar-brand href="#">Kulineran</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <router-link class="nav-link" to="/">Home</router-link>
            </li>
            <li class="nav-item">
              <router-link class="nav-link" to="/foods">Foods</router-link>
            </li>
          </ul>
      </b-navbar-nav>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <li class="nav-item">
          <router-link class="nav-link" to="/keranjang">
          Keranjang
          <b-icon-cart></b-icon-cart>
          <span class="badge badge-primary ml-2">{{ updateKeranjang ? updateKeranjang.length : jumlah_pesanans.length }}</span>
          </router-link>
        </li>
      </b-navbar-nav>
    </b-collapse>
    </div>
  </b-navbar>
</div>
  <!-- <nav class="navbar navbar-expand-lg bg-body-tertiary">
    <div class="container">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Kulineran</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <router-link class="nav-link" to="/">Home</router-link>
            </li>
            <li class="nav-item">
              <router-link class="nav-link" to="/foods">Foods</router-link>
            </li>
          </ul>

          <ul class="navbar-nav ml-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <router-link class="nav-link" to="/keranjang">
              Keranjang
              <b-icon-cart></b-icon-cart>
              <span class="badge badge-primary ml-2">{{ updateKeranjang ? updateKeranjang.length : jumlah_pesanans.length }}</span>
              </router-link>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </nav> -->
</template>

<script>
import axios from "axios";

export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Navbar',
    data() {
      return {
        jumlah_pesanans: [],
      }
    },
    props: ['updateKeranjang'],
    methods: {
      setJumlah(data) {
        this.jumlah_pesanans = data
      }
    },
    mounted() {
      axios
      .get("http://localhost:3000/keranjangs")
      .then((response) => this.setJumlah(response.data))
      .catch((error) => console.log(error))
    }
}
</script>

<style>

</style>