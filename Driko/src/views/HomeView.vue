<script setup>
import cocktailCardVue from '../components/cocktailCard.vue';
</script>

<template>
  <img src="/bg-img.jpg" alt="" class="bg-img">
  <header class="hero-banner">
    <div class="text-wraper">
      <h1 class="hero-title">Become a pro in <br> <strong>cocktails</strong> !</h1>
      <p class="hero-text">With Driko, always discover new drinks and how to do them 😉</p>
      <button class="cta">Discover cocktails</button>
    </div>
  </header>
  <main>
    <div class="cocktail-card-wraper">
      <cocktailCardVue />
      <cocktailCardVue />
      <cocktailCardVue />
      <cocktailCardVue />
    </div>
  </main>
</template>

<style scoped>
  .hero-banner{
    min-width: 100%;
    position: relative;
    height: calc(78vh - 70px);
  }

  .bg-img {
    position: absolute;
    inset: -20% 0 auto auto;
    width: 80vw;
    -webkit-mask-image: linear-gradient(-90deg, black 40%, transparent 80%);
    mask-image: linear-gradient(-90deg, black 40%, transparent 80%);
    -webkit-mask-repeat: no-repeat;
    mask-repeat: no-repeat;
  }
  .text-wraper{
    margin-top: 10rem;
    margin-left: 7rem;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }
  .hero-title{
    font-size: 3.5rem;
    font-weight: 500;
    color: #f8f7f5;
    line-height: 3.7rem;
  }

  .hero-text{
    font-size: 1.5rem;
    max-width: calc(40vw - 7rem);
  }

  .hero-title > strong {
    color: #c037ffd8;
    padding: 0 .2rem;
    font-weight: 700;
  }

  .cta{
    padding: 1rem 2.5rem;
    width: fit-content;
    border: 0;
    background-color: #c037ffd8;
    color: #f8f7f5;
    text-transform: uppercase;
    font-weight: 600;
    border-radius: .2rem;
    transition: .4s;
    cursor: pointer;
    margin-top: 1.5rem;
    font-family: 'Quicksand';
  }

  .cta:hover{
    background-color: #dd189bd8;
    
  }

  .cocktail-card-wraper{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    justify-items: center;
    row-gap: 5rem;
    background-color: #772c52;
    padding: 5rem 0;
  }
</style>
