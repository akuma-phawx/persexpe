<script setup lang="ts">
import { RouterLink } from "vue-router";
</script>
<template>
  <nav>
    <div class="navbar bg-light">
      <div class="mx-4">
        <h2>PersExpe</h2>
      </div>
      <div class="mx-4">
        <RouterLink class="text-decoration-none mx-2" to="/">Home</RouterLink>
        <RouterLink class="text-decoration-none" to="/new">New</RouterLink>
        <RouterLink class="text-decoration-none mx-2" to="/history"
          >History</RouterLink
        >
        <RouterLink class="text-decoration-none mr-2" to="/debts"
          >Debts</RouterLink
        >
      </div>
    </div>
  </nav>
</template>
