<script setup>
  import Product from './Product.vue'
  import {ref} from 'vue' // es: let pippo = ref('ciao') pippo viene monitorata, quando faccio ref utilizza un proxy, diventa un oggetto che avrà al suo interno
  //una proprietà value che avrà valore ciao all'interno dello script infatti diciamo pippo.value, nel template non serve

  let products = ref([
    {
      id:'1',
      name:'Airpods',
      rating:2,
      imageurl : 'https://i.ibb.co/TvVNyn0/452378071-2281412335699589-7762790786766948773-n.jpg',
      description : 'Ear pods made by Apple Inc.',
      pubDate : 'September 17, 2016'
    },
    {
      id:'2',
      name:'Kindle',
      rating:2,
      imageurl : 'https://i.ibb.co/TvVNyn0/452378071-2281412335699589-7762790786766948773-n.jpg',
      description : 'Ebook tablet, made by Amazon',
      pubDate : 'November 19, 2007'
    },
    {
      id:'3',
      name:'Book: Il Franchising dietro le quinte',
      rating:2,
      imageurl : 'https://i.ibb.co/TvVNyn0/452378071-2281412335699589-7762790786766948773-n.jpg',
      description : 'Bestseller of the famous writer Pasquale Olandese',
      pubDate : 'June 14, 2018'
    },
  ])
  let isValid = ref(false)
</script>
<template>
  <!-- <h1>Products</h1> -->
  <!-- <h1>Products: {{ category }} by {{ username }}</h1> -->
  <!-- <h1>Products: {{ category + 'by' + username }} </h1> -->
  <!-- <h1>{{ username ? username : 'no username' }}</h1> -->
  <div v-for="product in products" :key="product.id">
    <Product :data="product" />
  </div>
  <button type="button" class="btn btn-danger" v-bind:disabled="!isValid">Clicca qui</button>
</template>
