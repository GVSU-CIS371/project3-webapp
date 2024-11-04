<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" :creamer="selectedCreamer" :syrup="selectedSyrup" :baseBeverage="selectedBaseBeverage" />
    <ul>
      <li>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>
      </li>
    </ul>
    <h3>Creamer</h3>
    <ul>
      <li>
        <template v-for="creamer in creamers" :key="creamer">
          <label>
            <input
              type="radio"
              name="creamer"
              :id="`r${creamer}`"
              :value="creamer"
              v-model="selectedCreamer"
            />
            {{ creamer }}
          </label>
        </template>
      </li>
    </ul>

    <h3>Syrup</h3>
    <ul>
      <li>
        <template v-for="syrup in syrups" :key="syrup">
          <label>
            <input
              type="radio"
              name="syrup"
              :id="`r${syrup}`"
              :value="syrup"
              v-model="selectedSyrup"
            />
            {{ syrup }}
          </label>
        </template>
      </li>
    </ul>

    <h3>Base Beverage</h3>
    <ul>
      <li>
        <template v-for="base in baseBeverages" :key="base">
          <label>
            <input
              type="radio"
              name="baseBeverage"
              :id="`r${base}`"
              :value="base"
              v-model="selectedBaseBeverage"
            />
            {{ base }}
          </label>
        </template>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import Beverage from "./components/Beverage.vue";
import { temps, currentTemp } from "./stores/beverage";
import { ref } from 'vue';

const creamers = ["No Creamer", "Milk", "Cream", "Half & Half"];
const syrups = ["No Syrup", "Vanilla", "Caramel", "Hazelnut"];
const baseBeverages = ["Coffee", "Green Tea", "Black Tea"];

const selectedCreamer = ref("No Creamer");
const selectedSyrup = ref("No Syrup");
const selectedBaseBeverage = ref("Coffee");
</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}
</style>
