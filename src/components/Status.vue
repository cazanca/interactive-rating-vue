<script setup>
import {defineProps} from 'vue'
    defineProps(['rate'])
</script>
<template>
    <div class="status__image">
        <img src="../assets/images/illustration-thank-you.svg" alt="Thank you Image">
    </div>
    <div class="rating__container">
        <span class="rating__value">
        You Selected {{rate}} out of 5
        </span>
    </div>

    <h2 class="status__title">Thank You</h2>
    <p class="status__description">
        We appreciate you taking the time to give a rating. If you ever need more support, don’t hesitate to get in touch! 
    </p>
</template>