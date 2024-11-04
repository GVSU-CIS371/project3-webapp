<template>
  <div :class="baseClass" class="baseBeverage"></div>
</template>

<script setup lang="ts">
import { computed, defineProps } from 'vue';

const props = defineProps<{ baseBeverage: string }>();

const baseClass = computed(() => {
  switch (props.baseBeverage) {
    case "Coffee":
      return "coffee";
    case "Green Tea":
      return "green-tea";
    case "Black Tea":
      return "black-tea";
    default:
      return "";
  }
});
</script>

<style scoped>
.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  border-radius: 0.05em 0.05em 2.2em 2.2em;
  transition: background-color 0.5s ease;
}

.coffee {
  background-color: #4b2e2b;
}

.green-tea {
  background-color: #b7c59b;
}

.black-tea {
  background-color: #593d2b;
}

</style>
