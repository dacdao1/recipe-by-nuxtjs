<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :atl="recipe.title" />
    </div>

    <p>
      {{ recipe.descriptionText }}
    </p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "Fish Dish ",
              previewText: "Come get your fish here!!",
              descriptionText: "This is a really tasty meal!",
              thumbnail:
                "https://www.mensjournal.com/wp-content/uploads/mf/_main_chicken_2.jpg"
            },
            {
              id: "2",
              title: "Pancakes ",
              previewText: "Come get your pancakes here!!",
              descriptionText: "This is a really tasty meal!",
              thumbnail:
                "https://www.bbcgoodfood.com/sites/default/files/styles/recipe/public/recipe/recipe-image/2017/05/american-style-pancakes.jpg?itok=_tikdZhR"
            }
          ].find(el => el.id === context.params.id)
        });
      }, 1500);
    });
  }
};
</script>
<style scoped>
.single-recipe {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}
.recipe-image {
  width: 100%;
  height: 100%;
}
</style>
