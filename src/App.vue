<script>
import TheHeader from './components/TheHeader.vue';
import TheFooter from './components/TheFooter.vue';

export default {
  components: {
    TheHeader,
    TheFooter
  }
}
</script>

<template>
  <!-- Header -->
  <TheHeader />

  <!-- Main -->
  <main>
    <div class="container container-xl p-5">

      <h1> Content goes here </h1>
    </div>
  </main>

  <!-- Footer -->
  <TheFooter />
</template>

<style lang="scss">
@use "./styles/general.scss";
@use "./styles/partials/variables";

main {
  background-color: variables.$color-secondary-dark;

  h1 {
    color: white;
  }
}
</style>
