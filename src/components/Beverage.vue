<template>
  <Mug>
    <Cold v-if="isIced" />
    <Hot v-else />
    <Contents>
      <template v-slot:top>
        <Creamer v-if="creamer !== 'No Creamer'" :creamer="creamer" />
      </template>
      <template v-slot:mid>
        <Syrup v-if="syrup !== 'No Syrup'" :syrup="syrup" />
      </template>
      <template v-slot:bottom>
        <Base :baseBeverage="baseBeverage" />
      </template>
    </Contents>
  </Mug>
</template>

<script setup lang="ts">
import Contents from "./Contents.vue";
import Mug from "./Mug.vue";
import Syrup from "./Syrup.vue";
import Base from "./Base.vue";
import Creamer from "./Creamer.vue";
import Hot from "./Hot.vue";
import Cold from "./Cold.vue";

const props = defineProps<{
  isIced: boolean;
  baseBeverage: string;
  creamer: string;
  syrup: string;
}>();
</script>
