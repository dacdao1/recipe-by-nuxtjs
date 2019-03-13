<template>
  <section class="recipes">
    <!--this is the first box of recipe and title-->
    <Recipe
      v-for="recipe in recipes"
      :key="recipe.id"
      :thumbnail="recipe.thumbnail"
      :title="recipe.title"
      :id="recipe.id"
      :previewText="recipe.previewText"
    />
  </section>
</template>

<script>
import Recipe from "@/components/Recipe";
export default {
  components: {
    Recipe
  },
  asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: "1",
              title: "Fish Dish ",
              previewText: "Come get your fish here!!",
              thumbnail:
                "https://www.mensjournal.com/wp-content/uploads/mf/_main_chicken_2.jpg"
            },
            {
              id: "2",
              title: "Pancakes ",
              previewText: "Come get your pancakes here!!",
              thumbnail:
                "https://www.bbcgoodfood.com/sites/default/files/styles/recipe/public/recipe/recipe-image/2017/05/american-style-pancakes.jpg?itok=_tikdZhR"
            }
          ]
        });
      }, 1500);
    });
  }
};
</script>
<style scoped>
.recipes {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}
</style>
