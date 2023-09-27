<template>
  <section>
    <div class="container">

      <div class="heading">
       About Us
      </div>
    </div>
  </section>
</template>

<script>
import categoryCardData from "../data/categoryCard";
import client from "../api";

export default {
  name: "AboutPage",
  data() {
    return {
      isLoading: false,
      isShowModal: false
    };
  },
  methods: {
  },
};
</script>

<style lang="scss">

@media screen and (max-width: 768px) {
}
</style>
