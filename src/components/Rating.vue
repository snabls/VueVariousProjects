<script setup>
  import {ref} from 'vue'
  const props = defineProps({initialRating:Number})

  let rating = ref(props.initialRating)
  let color = ref('orange')

  function assignRating(r)
  {
    rating.value = r
  }
</script>
<template>
  <h3>Rating : {{ rating }}</h3>
  <span :style="{color : color}" v-on:click="assignRating(1)">
    <i v-if="rating >= 1" class="bi bi-star-fill"></i>
    <i v-else class="bi bi-star"></i>
  </span>
  <span :style="{color : color}" v-on:click="assignRating(2)">
    <i v-if="rating >= 2" class="bi bi-star-fill"></i>
    <i v-else class="bi bi-star"></i>
  </span>
  <span :style="{color : color}" v-on:click="assignRating(3)">
    <i v-if="rating >= 3" class="bi bi-star-fill"></i>
    <i v-else class="bi bi-star"></i>
  </span>
  <span :style="{color : color}" v-on:click="assignRating(4)">
    <i v-if="rating >= 4" class="bi bi-star-fill"></i>
    <i v-else class="bi bi-star"></i>
  </span>
  <span :style="{color : color}" v-on:click="assignRating(5)">
    <i v-if="rating >= 5" class="bi bi-star-fill"></i>
    <i v-else class="bi bi-star"></i>
  </span>
</template>
