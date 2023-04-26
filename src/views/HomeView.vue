<script setup lang="ts">
  import { ref } from "vue";
  import { Icon } from "@iconify/vue";
  import ContactItem from "@/components/contacts/ContactItem.vue"

  const msg = ref<string>("World");
</script>

<template>
  <section class="flex-1 flex">
      <div class="bg-gray-100 rounded-lg p-2 w-full h-[2000px] flex flex-col divide-y-2">
        <ContactItem/>
        <ContactItem/>
        <ContactItem/>
        <ContactItem/>
    </div>
  </section>
  
  <div class="pointer-events-none [&>*]:pointer-events-auto flex fixed justify-end p-4 inset-x-0 bottom-0">
    <button class="btn btn-circle">
      <Icon class="text-3xl" icon="mdi:add"/>
    </button>
  </div>
</template>
