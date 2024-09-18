<template>
  <div>
    <Navbar />
    <slot />
  </div>
</template>

<script setup lang="ts">
import Navbar from "~/components/navbar/navbar.vue";
</script>
