<script setup>
import Rating from './Rating.vue'
import { ref } from 'vue'
const props = defineProps({ data: Object })
</script>
<template>
  <!--<h2>{{ props.id }}</h2>
  <h3>{{ props.name }}</h3>
  <Rating :initial-rating="props.rating" />!-->
  <div class="card" style="width: 18rem">
    <img src="https://picsum.photos/200" class="card-img-top" alt="..." />
    <div class="card-body">
      <h5 class="card-title">{{ props.data.id }}, {{ props.data.name }}</h5>
      <p class="card-text">
        {{ props.data.description }} <br />
        Published on {{ props.data.pubDate }}
      </p>
      <Rating initial-rating="{{props.data.rating}}" /> <br />
      <a href="..." class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
</template>
