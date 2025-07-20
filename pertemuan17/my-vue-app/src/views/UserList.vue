<template>
  <Layout>
    <h2 class="text-2xl font-semibold mb-6 text-blue-800">Daftar User</h2>

    <div v-if="loading" class="text-gray-500 italic">Memuat data user...</div>

    <table v-else class="w-full table-auto border border-collapse text-sm md:text-base">
      <thead class="bg-blue-100 text-left">
        <tr>
          <th class="border px-4 py-2">Avatar</th>
          <th class="border px-4 py-2">Nama</th>
          <th class="border px-4 py-2">Email</th>
          <th class="border px-4 py-2">Aksi</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id" class="hover:bg-gray-50">
          <td class="border px-4 py-2">
            <img :src="user.avatar" alt="avatar" class="w-12 h-12 rounded-full object-cover" />
          </td>
          <td class="border px-4 py-2 font-medium">{{ user.name }}</td>
          <td class="border px-4 py-2">{{ user.email }}</td>
          <td class="border px-4 py-2">
            <router-link
              :to="`/edit/${user.id}`"
              class="text-blue-600 hover:underline font-semibold"
            >
              Edit
            </router-link>
          </td>
        </tr>
      </tbody>
    </table>
  </Layout>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Layout from '../components/Layout.vue'

const users = ref([])
const loading = ref(true)

onMounted(async () => {
  try {
    const res = await fetch('https://687d01b4918b64224330bbd0.mockapi.io/api/users/')
    users.value = await res.json()
  } catch (error) {
    console.error('Gagal memuat data user:', error)
  } finally {
    loading.value = false
  }
})
</script>
