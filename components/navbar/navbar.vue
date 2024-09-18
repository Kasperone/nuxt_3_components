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
        {{ menuLink.linkName }}
      </NuxtLink>
    </div>
  </div>
</template>

<script setup lang="ts">
const selectedMenuLinkIndex = ref(0);

const setSelectedMenuLinkIndex = (menuLinkIndex: number) =>
  (selectedMenuLinkIndex.value = menuLinkIndex);

const menuLinks = [
  { linkName: "Home", pagePath: "home" },
  { linkName: "Inputs", pagePath: "inputs" },
  { linkName: "Sliders", pagePath: "sliders" },
  { linkName: "Progress bars", pagePath: "progress-bars" },
  { linkName: "Loaders", pagePath: "loaders" },
];
</script>
