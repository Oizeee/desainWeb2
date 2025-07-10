<template>
  <div class="p-6 max-w-md mx-auto">
    <h1 class="text-xl font-bold mb-4">Buat Pengguna Baru</h1>
    <form @submit.prevent="submitForm" class="space-y-4">
      <div>
        <label class="block">Nama:</label>
        <input v-model="name" class="w-full p-2 border rounded" required />
      </div>
      <div>
        <label class="block">Email:</label>
        <input v-model="email" type="email" class="w-full p-2 border rounded" required />
      </div>
      <button type="submit" class="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600">
        Kirim
      </button>
    </form>

    <div v-if="responseId" class="mt-4 text-green-600">
      Pengguna berhasil dibuat! ID: {{ responseId }}
    </div>

    <router-link to="/" class="block mt-6 text-blue-500 hover:underline">← Kembali ke Daftar</router-link>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const responseId = ref(null)

async function submitForm() {
  const res = await fetch('https://jsonplaceholder.typicode.com/users', {
    method: 'POST',
    body: JSON.stringify({ name: name.value, email: email.value }),
    headers: { 'Content-Type': 'application/json' },
  })

  const data = await res.json()
  responseId.value = data.id
}
</script>
