<script setup lang="ts">
import { RouterView, RouterLink, useRoute } from "vue-router";
import { ref } from "vue";
import { Icon } from "@iconify/vue";
import { computed } from "@vue/reactivity";

const route = useRoute();
const linkWithHeaders = ["/", "/appointment"];
const showHeader = computed(() =>
  linkWithHeaders.includes(route.path.toLowerCase())
);
</script>

<template>
  <main class="flex flex-col bg-red-100 text-black relative">
    {{ showHeader + "" }}

    {{ route.path }}
    <header
      v-if="showHeader"
      class="p-4 flex items-center gap-2 sm:gap-3 md:gap-4 lg:gap-6"
    >
      <Icon icon="mdi:phone" />
      <span class="text-xl font-bold">Halo Guru</span>
      <div class="ml-auto">
        <Icon class="text-2xl" icon="mdi:search" />
      </div>
    </header>
    <section
      v-if="showHeader"
      class="h-12 bg-yellow-100 grid grid-cols-2 sticky top-0"
    >
      <RouterLink
        to="/"
        class="grid place-content-center btn-primary btn normal-case"
      >
        <div class="flex flex-col gap-1 justify-center items-center">
          <!-- <Icon icon="mdi:chat" /> -->
          <span class="font-bold">Chat</span>
        </div>
      </RouterLink>
      <RouterLink
        to="/appointment"
        class="grid place-content-center btn-primary btn normal-case"
      >
        <div class="flex flex-col gap-1 justify-center items-center">
          <!-- <Icon icon="mdi:book" /> -->
          <span class="font-bold">Appoinment</span>
        </div>
      </RouterLink>
    </section>
    <RouterView />
  </main>
</template>
