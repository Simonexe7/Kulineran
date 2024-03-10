<template>
  <div class="card shadow">
    <img :src="'assets/images/' + product.gambar" class="card-img-top" style="height: 15rem;" alt="..." />
    <div class="card-body">
      <h5 class="card-title">{{ product.nama }}</h5>
      <p class="card-text">
        Harga: Rp.{{ product.harga }}
      </p>
      <router-link :to="'/foods/'+product.id" class="btn btn-primary">Pesan</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardProduct",
  props: ["product"],
};
</script>

<style>
</style>