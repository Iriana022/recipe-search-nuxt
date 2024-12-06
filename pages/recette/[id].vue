<template>
    <div class="container">
        <div class="spacer"></div>
        <NuxtLink to="/">
            All recipes
        </NuxtLink>
            <h2 class="title">{{ meals[0].strMeal }}</h2>
        <div class="grid">
            <div>
                <div>
                    <img :src="meals[0].strMealThumb" alt="">
                </div>
            </div>
                <div>
                    <article>
                        <header>
                            <h5>Ingredients</h5>
                        </header>
                        <ul>
                            <li v-if="meals[0].strIngredient1">{{ meals[0].strIngredient1 }} 
                                <span v-if="meals[0].strMeasure1">{{ meals[0].strMeasure1 }}</span></li>
                            <li v-if="meals[0].strIngredient2">{{ meals[0].strIngredient2 }} 
                                <span v-if="meals[0].strMeasure2">{{ meals[0].strMeasure2 }}</span></li>
                            <li v-if="meals[0].strIngredient3">{{ meals[0].strIngredient3 }} 
                                <span v-if="meals[0].strMeasure3">{{ meals[0].strMeasure3 }}</span></li>
                            <li v-if="meals[0].strIngredient4">{{ meals[0].strIngredient4 }} 
                                <span v-if="meals[0].strMeasure4">{{ meals[0].strMeasure4 }}</span></li>
                            <li v-if="meals[0].strIngredient5">{{ meals[0].strIngredient5 }} 
                                <span v-if="meals[0].strMeasure5">{{ meals[0].strMeasure5 }}</span></li>
                            <li v-if="meals[0].strIngredient6">{{ meals[0].strIngredient6 }} 
                                <span v-if="meals[0].strMeasure6">{{ meals[0].strMeasure6 }}</span></li>
                            <li v-if="meals[0].strIngredient7">{{ meals[0].strIngredient7 }} 
                                <span v-if="meals[0].strMeasure7">{{ meals[0].strMeasure7 }}</span></li>
                            <li v-if="meals[0].strIngredient8">{{ meals[0].strIngredient8 }} 
                                <span v-if="meals[0].strMeasure8">{{ meals[0].strMeasure8 }}</span></li>
                            <li v-if="meals[0].strIngredient9">{{ meals[0].strIngredient9 }} 
                                <span v-if="meals[0].strMeasure9">{{ meals[0].strMeasure9 }}</span></li>
                            <li v-if="meals[0].strIngredient10">{{ meals[0].strIngredient10 }} 
                                <span v-if="meals[0].strMeasure10">{{ meals[0].strMeasure10 }}</span></li>
                            <li v-if="meals[0].strIngredient11">{{ meals[0].strIngredient11}} 
                                <span v-if="meals[0].strMeasure10">{{ meals[0].strMeasure11 }}</span></li>
                            <li v-if="meals[0].strIngredient12">{{ meals[0].strIngredient12 }} 
                                <span v-if="meals[0].strMeasure12">{{ meals[0].strMeasure12 }}</span></li>
                            <li v-if="meals[0].strIngredient13">{{ meals[0].strIngredient13 }} 
                                <span v-if="meals[0].strMeasure13">{{ meals[0].strMeasure13 }}</span></li>
                            <li v-if="meals[0].strIngredient14">{{ meals[0].strIngredient14 }} 
                                <span v-if="meals[0].strMeasure14">{{ meals[0].strMeasure14 }}</span></li>
                            <li v-if="meals[0].strIngredient15">{{ meals[0].strIngredient15 }} 
                                <span v-if="meals[0].strMeasure15">{{ meals[0].strMeasure15 }}</span></li>
                            <li v-if="meals[0].strIngredient16">{{ meals[0].strIngredient16 }} 
                                <span v-if="meals[0].strMeasure16">{{ meals[0].strMeasure16 }}</span></li>
                            <li v-if="meals[0].strIngredient17">{{ meals[0].strIngredient17 }} 
                                <span v-if="meals[0].strMeasure17">{{ meals[0].strMeasure17 }}</span></li>
                            <li v-if="meals[0].strIngredient18">{{ meals[0].strIngredient18 }} 
                                <span v-if="meals[0].strMeasure18">{{ meals[0].strMeasure18 }}</span></li>
                            <li v-if="meals[0].strIngredient19">{{ meals[0].strIngredient19 }} 
                                <span v-if="meals[0].strMeasure19">{{ meals[0].strMeasure19 }}</span></li>
                            <li v-if="meals[0].strIngredient20">{{ meals[0].strIngredient20 }} 
                                <span v-if="meals[0].strMeasure20">{{ meals[0].strMeasure20 }}</span></li>
                        </ul>
                    </article>
                </div>
        </div>
        <Preparations :video="meals[0].strYoutube" :instructions="meals[0].strInstructions"/>
    </div>        
</template>

<script setup>
import Preparations from "../../components/Preparations.vue" 

const route = useRoute()
const {data} = await useFetch(`https://www.themealdb.com/api/json/v1/1/lookup.php?i=${route.params.id}`)
const {meals} = data.value

</script>

<style scoped>
    .title{
        margin-top: 40px;
        margin-bottom: 50
        px;
    }
    li{
        display: flex;
        justify-content: space-between;
    }
    ul{
        padding-left: 0;
    }
    .spacer{
        padding-block: 25px;
    }
</style>