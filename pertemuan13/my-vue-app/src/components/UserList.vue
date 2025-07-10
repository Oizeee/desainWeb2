<template>
  <div class="p-6">
    <h1 class="text-xl font-bold mb-4">Daftar Pengguna</h1>
    <ul class="space-y-2">
      <li v-for="user in users" :key="user.id" class="border p-4 rounded">
        <router-link :to="'/user/' + user.id" class="text-blue-600 hover:underline">
          {{ user.name }}
        </router-link>
      </li>
    </ul>
    <router-link to="/create" class="inline-block mt-6 text-white bg-green-500 px-4 py-2 rounded hover:bg-green-600">
      Tambah Pengguna
    </router-link>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const users = ref([])

onMounted(async () => {
  const res = await fetch('https://jsonplaceholder.typicode.com/users')
  users.value = await res.json()
})
</script>
