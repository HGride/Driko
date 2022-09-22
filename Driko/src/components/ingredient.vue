<template>
    <div class="wraper">
        <img src="/ingredients.png" alt="cocktail shaker">
        <slot name="name"></slot>
    </div>
</template>

<style scoped>
    .wraper{
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>