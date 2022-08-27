<template>
  <div>
    <Header @goTo="goTo($event)" />
    <Content :new-page="newPage" :key="updateContent" />
    <Footer />
  </div>
</template>

<script>
  import Header from "./components/Header.vue";
  import Footer from "./components/Footer.vue";
  import Content from "./components/Content.vue";
  export default {
    name: "App",
    components: { Header, Content, Footer },
    data() {
      return {
        newPage: "MainPage",
        updateContent: 0,
      };
    },
    methods: {
      goTo(page) {
        this.newPage = page;
        this.updateContent++;
      },
    },
  };
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: black;
  }

  body {
    background-color: #f83b2f;
  }

  * {
    padding: 0;
    margin: 0;
  }
</style>
