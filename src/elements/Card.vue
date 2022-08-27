<template>
  <div class="flip-card-inner">
    <div class="flip-card-front">
      <div>?</div>
    </div>
    <div class="flip-card-back">
      <img :src="require('../assets/' + cardImage)" class="card-image" />
    </div>
  </div>
</template>

<script>
  import { ref } from "vue";
  export default {
    props: {
      image: String,
    },
    setup(props) {
      const cardImage = ref(props.image);

      return { cardImage };
    },
  };
</script>

<style>
  .flip-card {
    background-color: transparent;
    width: 270px;
    height: 400px;
    perspective: 1000px;
    border-radius: 10px;
  }

  .card-image {
    width: 270px;
    height: 400px;
    object-fit: cover;
    border-radius: 10px;
  }

  @media screen and (max-width: 768px) {
    .flip-card {
      width: 100%;
    }

    .card-image {
      width: 100%;
    }
  }

  .flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    border-radius: 10px;
    text-align: center;
    transition: transform 0.6s;
    transform-style: preserve-3d;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  }

  .flip-card:hover .flip-card-inner {
    transform: rotateY(180deg);
  }

  .flip-card-front,
  .flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 10px;
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;
  }

  .flip-card-front {
    background-color: #f83b2f;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 190px;
    color: rgb(255, 255, 255);
    font-family: "Bungee Shade", cursive;
    font-weight: bold;
    border: 5px solid white;
  }

  .flip-card-back {
    color: rgb(231, 231, 231);
    border-radius: 10px;
    transform: rotateY(180deg);
  }
</style>
