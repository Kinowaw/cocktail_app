<template>
  <div class="btn-container" v-on:click="toggleModale">
    <button class="btn-content">Content</button>
  </div>
  <div class="bloc-modale" v-if="revele">
    <div class="modal-header">
      <div class="title">
        <h1>{{ cocktail.strDrink }}</h1>
      </div>
      <button v-on:click="toggleModale" class="btn-modale">&times;</button>
    </div>
    <div class="modal-body">
      <h2>Category</h2>
      {{ cocktail.strCategory }}
    </div>
    <div class="modal-body">
      <h2>Type</h2>
      {{ cocktail.strAlcoholic }}
    </div>
    <div class="modal-body">
      <h2>Description</h2>
      {{ cocktail.strInstructions }}
    </div>
    <div class="modal-body">
      <h2>Ingredients</h2>
      <ul>
        <li v-for="ingredian in ingredien" :key="ingredian">
          {{ ingredian }}
        </li>
      </ul>
    </div>
  </div>
  <div id="overlay"></div>
</template>

<script>
export default {
  name: "ModalePopup",
  props: {
    revele: Boolean,
    toggleModale: Function,
    cocktail: [Array, Object],
    ingredien: [Array, Object],
  },
};
</script>
