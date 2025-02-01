<template>
  <div class="q-pa-md" style="max-width: t00px">
    <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-md">
      <q-input v-model="fname" label="First Name" />
      <q-input v-model="lname" label="Last Name" />
      <q-input v-model="username" label="Username" />
      <q-input v-model="password" label="Password" />
      <q-input v-model="email" label="Email" />
      <q-input v-model="avatar" label="Avatar" />
      <q-btn label="Submit" type="submit" color="primary" />
    </q-form>
  </div>
</template>

<script setup>
import { ref } from "vue";

// ข้อมูล API จาก https://www.melivecode.com/
const fname = ref('Cat')
const lname = ref('Chat')
const username = ref('cat.chat@melivecode.com')
const password = ref('1234')
const email = ref('cat.chat@melivecode.com')
const avatar = ref('https://www.melivecode.com/users/cat.png')

const onSubmit = () => {
    alert(fname.value)
};
</script>
