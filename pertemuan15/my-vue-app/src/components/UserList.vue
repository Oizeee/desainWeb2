<template>
  <div>
    <h2 class="text-xl font-bold mb-4">Daftar Pengguna (JSONPlaceholder API)</h2>

    <div v-if="users.length === 0">Loading data...</div>

    <div v-else class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
      <div
        v-for="user in users"
        :key="user.id"
        class="bg-white p-4 shadow rounded"
      >
        <p class="font-semibold">{{ user.name }}</p>
        <p class="text-sm text-gray-600">{{ user.email }}</p>
        <p class="text-sm text-gray-600">{{ user.phone }}</p>
        <p class="text-sm text-gray-600 italic">{{ user.website }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const users = ref([])

onMounted(async () => {
  try {
    const res = await fetch('https://jsonplaceholder.typicode.com/users')
    const data = await res.json()
    console.log('DATA:', data)
    users.value = data
  } catch (error) {
    console.error('Gagal mengambil data:', error)
  }
})
</script>
