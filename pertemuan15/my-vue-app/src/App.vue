<template>
  <div class="min-h-screen flex flex-col">
    <Navbar />

    <main class="flex-1 container mx-auto p-4">
      <UserList />
    </main>

    <Footer />
  </div>
</template>

<script setup>
import Navbar from './components/Navbar.vue'
import Footer from './components/Footer.vue'
import UserList from './components/UserList.vue'
</script>
