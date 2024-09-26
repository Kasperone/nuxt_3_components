<template>
  <div class="c-navbar">
    <div class="flex justify-center pt-10 gap-10">
      <NuxtLink
        v-for="(menuLink, menuLinkIndex) in menuLinks"
        :key="menuLinkIndex"
        :to="`/${menuLink.pagePath}`"
        :class="{ 'text-gray-200': menuLinkIndex === selectedMenuLinkIndex }"
        class="uppercase text-gray-500 text-xl"
        @click="setSelectedMenuLinkIndex(menuLinkIndex)"
      >
        {{ menuLink.label }}
      </NuxtLink>
    </div>
  </div>
</template>

<script setup lang="ts">
const selectedMenuLinkIndex = ref(0);

const setSelectedMenuLinkIndex = (menuLinkIndex: number) =>
  (selectedMenuLinkIndex.value = menuLinkIndex);

const menuLinks = [
  { label: "Home", pagePath: "home" },
  { label: "Inputs", pagePath: "inputs" },
  { label: "Sliders", pagePath: "sliders" },
  { label: "Progress bars", pagePath: "progress-bars" },
  { label: "Loaders", pagePath: "loaders" },
];
</script>
