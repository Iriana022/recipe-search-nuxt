<template>
    <div v-if="data" class="meals">
        <article class="meals-item" v-for="recipe in data.meals" :key="recipe.idMeal">
            <header><h6>{{ recipe.strMeal }}</h6></header>
            <img :src="recipe.strMealThumb" alt="">
            <footer>
                <NuxtLink :to="`/recette/${recipe.idMeal}`">
                    <button class="outline secondary">See recipes</button>
                </NuxtLink>
            </footer>
        </article>
    </div>
    <div v-else>
        <article aria-busy="true"></article>
    </div>
</template>

<script setup>
    const {data} = await useFetch('https://www.themealdb.com/api/json/v1/1/filter.php?a=Italian')
</script>

<style scoped>
.meals{
    display: flex;
    flex-wrap: wrap;
}
.meals-item{
    max-width: 33%;
}
@media(max-width:767px)
{
    .meals-item{
        max-width: 50%;        
    }
}
</style>