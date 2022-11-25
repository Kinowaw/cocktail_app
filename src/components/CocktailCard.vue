<template>
  <div class="card">
    <div class="card-header">
      <img :src="`${drink.strDrinkThumb}`" alt="Cocktail image" />
    </div>
    <div class="card-body">
      <span class="tag tag-teal">{{ drink.strCategory }}</span>
      <h2>{{ drink.strDrink }}</h2>
      <h3>{{ drink.strAlcoholic }}</h3>
      <div class="description">
        <p>{{ drink.strInstructions }}</p>
        <modal-Popup
          :cocktail="drink"
          :ingredien="ingredient"
          :revele="revele"
          :toggleModale="toggleModale"
        ></modal-Popup>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import ModalPopup from "./ModalPopup.vue";

export default {
  name: "CocktailCard",

  data() {
    return {
      drink: [],
      ingredient: [],
      revele: false,
    };
  },

  components: {
    ModalPopup,
  },

  methods: {
    toggleModale: function () {
      this.revele = !this.revele;
    },
  },

  async created() {
    var response = await axios.post(
      "https://www.thecocktaildb.com/api/json/v1/1/random.php"
    );
    this.drink = response.data.drinks[0];
    console.log(this.drink);

    for (var i = 1; i <= 15; i++) {
      this.ingredient.push(this.drink["strIngredient" + i]);
    }
  },
};
</script>
