<template>
  <div class="p-6">
    <h1 class="text-xl font-bold mb-4">Detail Pengguna</h1>
    <div v-if="user">
      <p><strong>Nama:</strong> {{ user.name }}</p>
      <p><strong>Email:</strong> {{ user.email }}</p>
      <p><strong>Telepon:</strong> {{ user.phone }}</p>
    </div>
    <router-link to="/" class="mt-4 inline-block text-blue-500 hover:underline">← Kembali</router-link>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { useRoute } from 'vue-router'

const user = ref(null)
const route = useRoute()

onMounted(async () => {
  const res = await fetch(`https://jsonplaceholder.typicode.com/users/${route.params.id}`)
  user.value = await res.json()
})
</script>
