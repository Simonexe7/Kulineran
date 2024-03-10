<template>
  <div class="pesanan-sukses">
    <Navbar />
    <div class="container">
        <div class="d-flex justify-content-center align-items-center">
            <div class="row">
                <div class="col">
                    <div class="d-flex justify-content-center">
                        <img src="assets/images/pesanan-sukses.png" class="img-fluid" style="height:20rem">
                    </div>
                    <h2 align="center"><strong>Pesanan Sukses!</strong></h2>
                    <h4 align="center">Terimakasih sudah memesan</h4>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";

export default {
  name: "PesananSukses",
  components: {
    Navbar,
  },
};
</script>

<style>
</style>