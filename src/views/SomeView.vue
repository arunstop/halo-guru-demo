<script setup lang="ts">
import { useRoute } from "vue-router";

const path = useRoute().path;
</script>

<template>
  <div>{{ path }}</div>
</template>
