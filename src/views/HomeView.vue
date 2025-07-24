<template>
  <h1>Home Page</h1>
  <GoToButton to="/about">Go to About</GoToButton>

  <button @click.prevent="() => (showAlert = true)">Open Alert Modal</button>
  <AlertModal
    v-if="showAlert"
    title="This is an example title"
    message="This is an example message"
    confirmText="Okay"
    cancelText="Cancel"
    @confirm="printOK()"
    @cancel="() => (showAlert = false)"
  />
</template>
<script setup>
import { ref } from "vue";
import GoToButton from "@/components/GoToButton.vue";
import AlertModal from "@/modals/AlertModal.vue";

const showAlert = ref(false);

function printOK() {
  console.log("OK");
  showAlert.value = false;
}
</script>
