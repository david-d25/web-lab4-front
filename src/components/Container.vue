<template>
  <div class="container"><slot/></div>
</template>

<script>
  export default {}
</script>

<style scoped>
  .container {
    max-width: 100%;
    width: 1000px;
    margin: auto;
  }

  @media (max-width: 1104px) {
    .container {
      width: 800px;
    }
  }

  @media (max-width: 847px) {
    .container {
      width: calc(165px + 40vw);
    }
  }
</style>
