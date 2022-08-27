<template>
  <label class="container">
    <p class="ml-5">{{ checkText }}</p>
    <input type="checkbox" />
    <span class="checkmark"></span>
  </label>
</template>

<script>
  import { ref } from "vue";
  export default {
    props: {
      text: {
        type: String,
      },
    },
    setup(props) {
      const checkText = ref(props.text);

      return { checkText };
    },
  };
</script>

<style scoped>
  .container {
    display: block;
    position: relative;
    padding-left: 35px;
    margin-bottom: 25px;
    cursor: pointer;
    font-size: 35px;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
    text-align: left;
  }

  .container input {
    position: absolute;
    opacity: 0;
    cursor: pointer;
    height: 0;
    width: 0;
  }

  .checkmark {
    position: absolute;
    top: 0;
    left: 0;
    height: 35px;
    width: 35px;
    background-color: transparent;
    border: 2px solid white;
  }

  .container:hover input ~ .checkmark {
    background-color: transparent;
  }

  .container input:checked ~ .checkmark {
    background-color: transparent;
  }

  .checkmark:after {
    content: "";
    position: absolute;
    display: none;
  }

  .container input:checked ~ .checkmark:after {
    display: block;
  }

  .container .checkmark:after {
    left: 10px;
    top: 1px;
    width: 10px;
    height: 20px;
    border: solid white;
    border-width: 0 3px 3px 0;
    -webkit-transform: rotate(45deg);
    -ms-transform: rotate(45deg);
    transform: rotate(45deg);
  }
</style>
