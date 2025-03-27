<script setup>
  import {ref} from 'vue'
  const obj = ref(
    {
      x: {count:0},
      y:['abc','def']
    }
  )
  function incrementX()
  {
    obj.value.x.count++;
  }
  function addToY()
  {
    obj.value.y.push('nuovo elemento');
  }
</script>
<template>
  <div>
    <h3>Contatore X: {{ obj.x.count }}</h3>
    <button @click="incrementX">Incrementa X</button>
    <h3>Lista Y:</h3>
    <ul>
      <li v-for="(item,index) in obj.y" :key="index">{{ item }}</li>
    </ul>
    <button @click="addToY">Aggiungi a Y</button>
  </div>

</template>

