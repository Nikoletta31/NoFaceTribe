<template>
  <div class="text-5xl text-center font-bold title">
    <h2>Collection Preview</h2>
  </div>
  <div class="mt-15">
    <p>
      Please note that if you would like to purchase one of those amazinf
      images, we invite you to visit our
      <span class="link" @click="goToOpenSea">OpenSea</span> page.
    </p>
    <br />
    <p>
      We believe that there is nothing better than to rely on the safe
      communication based on trust and therefore we have decided to sell our
      items on the websites dedicated for these kind of transactions.
    </p>
  </div>
  <div class="gap-2 grid grid-cols-1 md:grid-cols-3 place-items-center mt-10">
    <div v-for="n in 39" :key="n">
      <img
        :src="require('../assets/OtherImages/' + (n + 602) + '.png')"
        alt="Avatar"
        class="card-style"
        style="width: 100%; height: 400px; object-fit: cover"
      />
    </div>
  </div>
</template>

<script>
  export default {
    computed: {},
    methods: {
      goToOpenSea() {
        window.location.href = "https://opensea.io/NoFaceTribe";
      },
    },
  };
</script>

<style>
  p {
    text-align: justify;
  }
  .title {
    margin: 40px 0;
  }
  .link {
    font-weight: bold;
    cursor: pointer;
    color: #f83b2f;
  }
  .card-style {
    border: 10px solid white;
    border-radius: 5px;
  }
</style>
