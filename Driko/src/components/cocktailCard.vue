<script>
    import axios from 'axios'

    export default{
        // Properties returned from data() become reactive state
        // and will be exposed on `this`.
        data(){
            return {
                info: {}
            }
        },

        // Methods are functions that mutate state and trigger updates.
        // They can be bound as event listeners in templates.
        methods: {
        },


        // Lifecycle hooks are called at different stages
        // of a component's lifecycle.
        // This function will be called when the component is mounted.
        mounted() {

            axios.get('https://www.thecocktaildb.com/api/json/v1/1/random.php')
            .then((res)=>{
                this.info = res.data.drinks[0]
                this.info.url = `/cocktails/${res.data.drinks[0].idDrink}`
            })
            .catch((err)=>{
                console.log(err);
            })
        }
    }
</script>

<template>
    <div class="card">
        <header>
            <img :src="info.strDrinkThumb" alt="cocktail's pict" class="card-img">
        </header>
        <main>
            <h1 class="card-title">{{ info.strDrink }}</h1>
            <p class="card-text">{{ info.strCategory }}</p>
            <p class="card-text">{{ info.strAlcoholic }}</p>
        </main>
        <footer>
            <a :href="info.url"><button class="card-btn">More 🍹</button></a>
        </footer>
    </div>
</template>

<style scoped>
    .card{
        display: flex;
        flex-direction: column;
        background-color: #c037ffd8;
        backdrop-filter: blur(15px);
        min-width: 20rem;
        max-width: 20rem;
        overflow: hidden;
        border-radius: .3rem;
    }

    .card-img{
        width: 100%;
        aspect-ratio: 1/1;
        filter: grayscale(.5) brightness(.7) blur(.5px);
        scale: 1.05;
        transition: .4s;
    }

    .card:hover .card-img {
        filter: grayscale(0) brightness(1) blur(0);
        scale: 1.09;
    }

    main{
        padding: 0 1rem;
    }

    .card-title{
        font-size: 1.5rem;
    }

    .card-text{
        color: rgb(194, 158, 183)
    }

    footer{
        padding: 2rem;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .card-btn{
        box-sizing: border-box;
        height: 3rem;
        width: 15rem;
        border: #fff solid 2px;
        border-radius: 5rem;
        color: #fff;
        background-color: transparent;
        cursor: pointer;
        font-family: 'Quicksand';
        font-size: 1.2rem;
    }


</style>