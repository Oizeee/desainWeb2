<template>
  <aside class="bg-gray-800 text-white w-64 min-h-screen p-4 hidden md:block">
    <nav>
      <ul class="space-y-2">
        <li>
          <RouterLink to="/" class="block p-2 hover:bg-gray-700 rounded">
            Dashboard
          </RouterLink>
        </li>
        <li>
          <RouterLink to="/products" class="block p-2 hover:bg-gray-700 rounded">
            Products
          </RouterLink>
        </li>
        <li>
          <RouterLink to="/about" class="block p-2 hover:bg-gray-700 rounded">
            About Us
          </RouterLink>
        </li>
        <li>
          <RouterLink to="/contact" class="block p-2 hover:bg-gray-700 rounded">
            Contact
          </RouterLink>
        </li>
      </ul>
    </nav>
  </aside>
</template>

<script setup>
import { RouterLink } from 'vue-router'
</script>