<script setup>
  import {ref} from 'vue'

  const email = ref('')
  const password = ref('')
  const validEmail = ref(false)
  const validPassword = ref(false)
  const emailMessage = ref('')
  const passwordMessage = ref('')

  function onSubmit(){
    validEmail.value = false
    if(email.value.length < 6)
    {
      emailMessage.value = "Email un va bene"
    }
    else if(email.value.indexOf(' ')){
      emailMessage.value = "Email un va bene"
    }
    else {
      emailMessage.value = ' '
      validEmail.value = true
    }
    validPassword.value = false
    if(password.value.length < 6)
    {
      passwordMessage.value = "Password un va bene"
    }
    else if(password.value.indexOf(' ')){
      passwordMessage.value = "Password un va bene"
    }
    else {
      passwordMessage.value = ' '
      validPassword.value = true
    }
    if(validEmail.value && validPassword.value) {
      email.value = ' '
      password.value = ''
      validEmail.value = false
      validPassword.value = false
    }
  }
</script>

<template>
  <form @submit.prevent="onSubmit">
    <div class="mb-3">
      <label for="exampleInputEmail" class="form-label">Email:</label>
      <input type="email" id="exampleInputEmail" v-model="email" />
    </div>
    <div v-if="emailMessage.length > 0" class="alert alert-danger"+{{emailMessage}}></div>
    <div class="mb-3">
      <label for="exampleInputPwd" class="form-label">Password:</label>
      <input type="password" id="exampleInputPwd" v-model="password" />
    </div>
    <div v-if="emailMessage.length > 0" class="alert alert-danger"+{{passwordMessage}}></div>
    <button type="submit" class="btn btn-primary">Submit</button>
  </form>
  <div class="card">
    <div class="card-body">
      Email : {{email}} <br>
      Password : {{password}}
    </div>
  </div>
</template>

<style scoped>

</style>
