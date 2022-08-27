<template>
  <div
    class="container-black bg-black py-48 px-72 text-2xl text-center text-white"
  >
    <component :is="showPage" @goTo="goTo($event)" />
  </div>
</template>

<script>
  import MainPage from "./MainPage.vue";
  import AboutPage from "./AboutPage.vue";
  import CollectionPage from "./CollectionPage.vue";
  import ContactPage from "./ContactPage.vue";
  import { ref } from "vue";

  export default {
    components: { MainPage, AboutPage, CollectionPage, ContactPage },
    emits: ["goTo"],
    props: {
      newPage: {
        type: String,
      },
    },
    setup(props) {
      let showPage = ref(props.newPage);

      function goTo(page) {
        showPage.value = page;
      }

      return { goTo, showPage };
    },
  };
</script>

<style scoped>
  @media screen and (max-width: 768px) {
    .container-black {
      padding: 80px 40px;
    }
  }
</style>
