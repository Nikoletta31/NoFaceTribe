<template>
  <div>
    <div>
      <div>
        Once upon a time it was a tribe, the face of who nobody has ever
        seen.<br /><br />
        <span class="link">They were wearing a mask. </span><br /><br />
        But not a usual mask that most of us got used to wear. <br /><br />
        <span class="link">A way different mask.</span>
      </div>
      <h2 class="text-5xl text-center mt-24 font-bold">But who are they?</h2>
      <div
        class="gap-4 grid grid-cols-1 md:grid-cols-3 place-items-center my-20"
      >
        <div v-for="image in images" :key="image" class="flip-card">
          <Card :image="image" />
        </div>
      </div>
      <h2 class="text-5xl text-center my-24 font-bold">
        Why do they hide their face?
      </h2>
      <div v-for="text in questions" :key="text">
        <Checkbox :text="text" />
      </div>
      <div>
        <button class="button-style" @click="showAnswer = true">
          Submit and check
        </button>
      </div>
      <div v-if="showAnswer" class="mt-10 text-left">
        The answer stays in secret until the last member of the tribe would sell
        his liberty for once.
      </div>
      <h2 class="text-5xl text-center my-24 font-bold">Want to know more?</h2>
      <div class="gap-4 grid grid-cols-1 md:grid-cols-2 place-items-center">
        <button
          class="button-style m-5"
          @click="$emit('goTo', 'CollectionPage')"
        >
          Collection
        </button>
        <button class="button-style m-5" @click="$emit('goTo', 'AboutPage')">
          About
        </button>
      </div>
    </div>
  </div>
</template>

<script>
  import Card from "../elements/Card.vue";
  import Checkbox from "../elements/Checkbox.vue";
  import { ref } from "vue";
  export default {
    components: { Card, Checkbox },
    setup() {
      const checked = ref(false);
      const showAnswer = ref(false);
      const images = ["noface3.png", "noface2.png", "noface1.png"];
      const questions = [
        "They want to stay anonymous",
        "The sun is their enemy",
        "This is the way",
      ];

      return { checked, showAnswer, images, questions };
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
