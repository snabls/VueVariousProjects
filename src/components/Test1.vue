<script setup>
  import { ref } from 'vue'

  const mappa = ref(new Map([
    ['chiave1', 'valore1'],
    ['chiave2', 'valore2']
    ]
  ));

  function aggiungiElemento(){
    const nuovaChiave = `chiave${mappa.value.size + 1}`
    mappa.value.set(nuovaChiave, `valore${mappa.value.size + 1}`)
  }
</script>

<template>
  <div>
    <button class="btn-primary" @click="aggiungiElemento">Aggiungi elemento</button>
  </div>
  <ul>
    <li v-for="[chiave,valore] in mappa" :key="chiave">
      Chiave: {{ chiave }}, Valore: {{ valore }}
    </li>
  </ul>
</template>

<style scoped>

</style>
