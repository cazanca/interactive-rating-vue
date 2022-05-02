<script setup>
import { ref, provide } from 'vue';
import Rating from './components/Rating.vue';
import Status from './components/Status.vue';

let isSubmitted = ref(false)
let rating = ref(0)

const updateRating = (value) =>{
  rating.value = value
}

const submit = () => {
  isSubmitted.value = !isSubmitted.value
}

provide('isSubmitted', {
  isSubmitted,
  submit
})
provide('rating', {
  rating,
  updateRating
})

</script>

<template>
    <div class="card">
      <Rating v-if="!isSubmitted" />
      <Status v-if="isSubmitted" :rate="rating" />
    </div>
</template>

<style>
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease-out;
}
</style>
