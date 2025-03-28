<script setup>
  import {ref, onBeforeMount} from 'vue'

  let users = ref([])
  let searchTerm = ref('greg')
  let isLoading = ref(false)

  async function fetchGitHubUsers(){
    const res = await fetch(`https://api.github.com/users?q=${searchTerm.value}`)
    const data = await res.json()
    isLoading.value = false
  }

  async function onSubmit(){
    isLoading.value = true
    users.value = await fetchGitHubUsers()
  }
  onBeforeMount(async () => users.value = await fetchGitHubUsers())
</script>

<template>
  <form @submit.prevent="onSubmit">
    <div class="mb-3">
      <input type="text" class="form-control" v-model="searchTerm"></input>
    </div>
    <button type="submit" class="btn btn-outline-info">Submit</button>
  </form>
  <div v-if="isLoading" class="spinner-border" role="status"></div>
  <table class="table">
    <thead>
    <tr>
      <th scope="col">Id</th>
      <th scope="col">Avatar</th>
      <th scope="col">Login</th>
      <th scope="col">URL</th>
    </tr>
    </thead>
    <tbody>
    <tr v-for="user in users">
      <th scope="row">{{ user.id }}</th>
      <td><img src="user.avatar_url" :alt="user.login" width="75" height="75"></td>
      <td><a :href="user.html_url">{{user.html_url}}</a></td>
    </tr>
    </tbody>
  </table>
</template>

<style scoped>

</style>
