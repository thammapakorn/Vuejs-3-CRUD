<template>
    <div class="q-pa-md" style="max-width: t00px">
      <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md">

      <q-input label="First Name" />
      <q-input label="Last Name" />
      <q-input label="Username" />
      <q-input label="Password" />
      <q-input label="Email" />
      <q-input label="Avatar" />
    </q-form>
    </div>

</template>

<script setup>
    const onSubmit = () =>{

    }
</script>
