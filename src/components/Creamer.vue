<template>
  <div :class="frothClass" class="froth">
    <div v-for="n in 5" :key="n" class="foam"></div>
  </div>
</template>

<script setup lang="ts">
import { computed, defineProps } from 'vue';

const props = defineProps<{ creamer: string }>();

const frothClass = computed(() => {
  switch (props.creamer) {
    case "Milk":
      return "milk-froth";
    case "Cream":
      return "cream-froth";
    case "Half & Half":
      return "half-half-froth";
    default:
      return "";
  }
});
</script>

<style lang="scss" scoped>
.froth {
  overflow: visible;
  transform: translateY(400%);
  position: relative;
  height: 20%;
  width: 100%;
  animation: pour-tea 2s 2s forwards;
}

.milk-froth {
  background-color: #f3ede5;
}

.cream-froth {
  background-color: #e6bb6c;
}

.half-half-froth {
  background-color: #f5e0ad;
}

.foam {
  display: block;
  background: #e4e0d2;
  border-radius: 30px;
  height: 40px;
  width: 40px;
  position: absolute;
  transition: background 0.5s ease;
}

.foam:nth-child(1) { top: 0px; left: -3px; }
.foam:nth-child(2) { top: 0px; left: 55px; }
.foam:nth-child(3) { width: 30px; height: 30px; border-radius: 40px; top: 3px; left: 30px; }
.foam:nth-child(4) { width: 30px; height: 30px; border-radius: 45px; top: 5px; right: -2px; }
.foam:nth-child(5) { top: 2px; right: 10px; }

</style>
