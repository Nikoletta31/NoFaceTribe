<template>
  <h2 class="text-5xl text-center my-20 font-bold">Contact us</h2>
  <p>
    If you have any questions or propositions, please feel free to contact us on
    our Twitter or Instagram Pages. The links to which you can find below.
  </p>
  <div class="gap-4 grid grid-cols-1 md:grid-cols-2 place-items-center mt-20">
    <button class="button-style m-5" @click="goToTwitter">Twitter</button>
    <button class="button-style m-5" @click="goToInstagram">Instagram</button>
  </div>
</template>

<script>
  export default {
    setup() {
      function goToTwitter() {
        window.location.href = "https://twitter.com/NoFaceTribe";
      }

      function goToInstagram() {
        window.location.href = "https://www.instagram.com/nofacetribe/";
      }

      return { goToTwitter, goToInstagram };
    },
  };
</script>

<style scoped>
  .button-style {
    padding: 15px 25px;
    background-color: transparent;
    color: white;
    border: 2px solid white;
    font-size: 25px;
    border-radius: 5px;
    cursor: pointer;
    margin-top: 10px;
    width: 100%;
  }

  @media screen and (min-width: 768px) {
    .button-style {
      width: 50%;
    }
  }

  .button-style:hover {
    background-color: white;
    color: black;
  }

  .link {
    color: #f83b2f;
  }
</style>
