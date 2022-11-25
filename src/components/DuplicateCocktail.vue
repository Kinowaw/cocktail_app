<template>
  <div class="container">
    <Cocktail-Card v-for="count in totalCount" :key="`${count}`" />
  </div>
</template>

<script>
import CocktailCard from "./CocktailCard.vue";

export default {
  name: "DuplicatedCocktail",
  components: {
    CocktailCard,
  },
  data() {
    return {
      totalCount: 3,
    };
  },
  methods: {
    duplicateEl() {
      this.totalCount++;
    },
  },
};
</script>
