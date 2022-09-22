<script>
    import axios from 'axios'
    import Ingredient from '../components/ingredient.vue'
    export default {
    data() {
        return {
            info: {}
        };
    },
    mounted() {
        axios.get(`https://www.thecocktaildb.com/api/json/v1/1/lookup.php?i=${this.$route.params.id}`)
            .then((res) => {
            this.info = res.data.drinks[0];
            this.info.ingredients = []
            for (let i = 1; i <= 15; i++) {
                this.info.ingredients.push({name: res.data.drinks[0].strIngredient})                
            }
        })
            .catch((err) => {
            console.log(err);
        });
    },
    components: { Ingredient }
}
    

</script>

<template>
    <section class="left">
        <img :src="info.strDrinkThumb" alt="drink thumb">
    </section>
    <section class="right">
        <h1 class="title">{{ info.strDrink }}</h1>
        <Ingredient v-for="ingredient in info.ingredient" :key="ingredient"><template #name></template></Ingredient>
    </section>
</template>

<style>
</style>
  