<template>
  <div class="min-h-screen flex flex-col">
    <Header />
    <div class="flex flex-1">
      <Sidebar />
      <main class="flex-1 p-4 bg-gray-50">
        <slot />
      </main>
    </div>
  </div>
</template>

<script setup>
import Header from './Header.vue'
import Sidebar from './Sidebar.vue'
</script>