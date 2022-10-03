<template>
  <form autocomplete="off">
    <ValidationProvider v-slot="{ errors }" rules="required|name">
      <v-text-field v-model="user.name" type="text" label="Enter your name" />
      <span class="text-red-500"> {{ errors[0] }}</span>
    </ValidationProvider>
    <ValidationProvider v-slot="{ errors }" rules="required|email">
      <v-text-field
        v-model="user.email"
        type="email"
        label="Enter your email"
      />
      <span class="text-red-500">{{ errors[0] }}</span>
    </ValidationProvider>
    <div>
      <p>Name: {{ user.name }}</p>
      <p>Email: {{ user.email }}</p>
    </div>
  </form>
</template>

<script lang="ts">
import { extend, ValidationProvider } from 'vee-validate'
import { defineComponent, reactive } from '@nuxtjs/composition-api'

extend('name', (name: string) => {
  if (name.length < 8) {
    return 'The name must be at least 8 characters' as any
  }
  return true
})

export default defineComponent({
  components: {
    ValidationProvider,
  },
  setup() {
    const user = reactive({
      name: '',
      email: '',
    })

    return {
      user,
    }
  },
})
</script>

<style scoped></style>
