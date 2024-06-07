<script>
import headerVue from "./components/header.vue";
import mainVue from "./components/main.vue";

export default {
  components: {
    headerVue,
    mainVue,
  },
};
</script>

<template>
  <div class="d-flex flex-column">
    <headerVue />
    <mainVue />
  </div>
</template>

<style lang="scss" scoped>
@use "./assets/scss/main.scss";
</style>
