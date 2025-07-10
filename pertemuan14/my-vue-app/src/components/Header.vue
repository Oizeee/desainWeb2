<template>
  <header class="bg-blue-600 text-white p-4 shadow-md">
    <div class="container mx-auto flex justify-between items-center">
      <h1 class="text-2xl font-bold">My Vue App</h1>
      <nav>
        <ul class="flex space-x-4">
          <li><RouterLink to="/" class="hover:text-blue-200">Home</RouterLink></li>
          <li><RouterLink to="/about" class="hover:text-blue-200">About</RouterLink></li>
          <li><RouterLink to="/contact" class="hover:text-blue-200">Contact</RouterLink></li>
          <li><RouterLink to="/products" class="hover:text-blue-200">Products</RouterLink></li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script setup>
import { RouterLink } from 'vue-router'
</script>