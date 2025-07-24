<template>
  <div class="modal-overlay" @click="$emit('cancel')">
    <div class="modal-box">
      <div class="alert-modal">
        <h2 v-if="title" class="alert-title">{{ title }}</h2>
        <p class="alert-message">{{ message }}</p>

        <div class="modal-actions">
          <button class="btn primary" @click="$emit('confirm')">
            {{ confirmText }}
          </button>
          <button class="btn secondary" @click="$emit('cancel')">
            {{ cancelText }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  message: {
    type: String,
    required: true,
  },
  confirmText: {
    type: String,
    default: "Okay",
  },
  cancelText: {
    type: String,
    default: "Cancel",
  },
});

defineEmits(["confirm", "cancel"]);
</script>
