<template>
  <div class="bg-black text-white py-12">
    ©<span>{{ currentYear }}</span> No Face Tribe
  </div>
</template>

<script>
  export default {
    setup() {
      const currentYear = new Date().getFullYear();

      return { currentYear };
    },
  };
</script>

<style scoped></style>
