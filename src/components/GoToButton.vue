<template>
  <router-link :to="to" class="goto-button">
    <slot></slot>
  </router-link>
</template>

<script setup>
defineProps({
  to: {
    type: [String, Object],
    required: true,
    default: null,
  },
});
</script>
