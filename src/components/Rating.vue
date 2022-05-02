<script setup>
    import { ref } from '@vue/reactivity';
    import { inject } from '@vue/runtime-core';
    import Card from './Card.vue';

    const {rating, updateRating} = inject('rating')
    const {submit} = inject('isSubmitted')

    const activeClass = (value) => {
        return rating.value == value ? 'active' : ''
    }
</script>
<template>
    <div class="rating-icon">
        <img src="../assets/images/icon-star.svg" alt="rating icon">
    </div>
    
    <h2 class="title">How did we do?</h2>
    <p class="description">Please let us know how we did with your support request. All feedback is appreciated to help us improve our offering!</p>
    
    <div class="rating__category">
        <button class="rating__category-button" @click="updateRating(1)" :class="activeClass(1)">1</button>
        <button class="rating__category-button" @click="updateRating(2)" :class="activeClass(2)">2</button>
        <button class="rating__category-button" @click="updateRating(3)" :class="activeClass(3)">3</button>
        <button class="rating__category-button" @click="updateRating(4)" :class="activeClass(4)">4</button>
        <button class="rating__category-button" @click="updateRating(5)" :class="activeClass(5)">5</button>
    </div>
    <button class="submit" @click="submit()">Submit</button>
</template>

