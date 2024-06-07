<script>
import headerVue from "./components/header.vue";
import mainVue from "./components/main.vue";
import imageDragger from "./components/image-dragger.vue";

export default {
  components: {
    headerVue,
    mainVue,
    imageDragger,
  },
};
</script>

<template>
  <div class="d-flex flex-column">
    <headerVue />
    <mainVue />
    <imageDragger />
  </div>
</template>

<style lang="scss" scoped>
@use "./assets/scss/main.scss";
</style>
