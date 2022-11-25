<template>
  <div>
    <Duplicate-Cocktail></Duplicate-Cocktail>
  </div>
</template>

<script>
import "./assets/style/style.scss";
import DuplicateCocktail from "./components/DuplicateCocktail.vue";

export default {
  name: "App",
  components: {
    DuplicateCocktail,
  },
};
</script>
