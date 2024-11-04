<template>
  <div :class="syrupClass" class="syrup"></div>
</template>

<script setup lang="ts">
import { computed, defineProps } from 'vue';

const props = defineProps<{ syrup: string }>();

const syrupClass = computed(() => {
  switch (props.syrup) {
    case "Vanilla":
      return "vanilla-syrup";
    case "Caramel":
      return "caramel-syrup";
    case "Hazelnut":
      return "hazelnut-syrup";
    default:
      return "";
  }
});
</script>

<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}

.vanilla-syrup {
  background-color: #f3e5ab;
}

.caramel-syrup {
  background-color: #d4a373;
}

.hazelnut-syrup {
  background-color: #b58e6c;
}

</style>
