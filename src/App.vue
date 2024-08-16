<script setup>
import { ref } from '../node_modules/vue'
import CrimeBox from "@/components/crimeBox.vue";
let data= ref(["Loading...", "Loading...", "Loading...", "Loading...", "Loading...", "Loading..."])
fetch('https://data.cityofchicago.org/resource/ijzp-q8t2.json?$limit=100')
    .then(async (d) => {data.value = await d.json()})
    .catch((error) => {data.value = "Error fetching data"})

</script>

<template>
    <div class="grid-container">
      <crime-box class="box" :data="data[0]" style="grid-column:1; grid-row:1;"></crime-box>
      <crime-box class="box" :data="data[1]" style="grid-column:2; grid-row:1;"></crime-box>
      <crime-box class="box" :data="data[2]" style="grid-column:3; grid-row:1;"></crime-box>
      <crime-box class="box" :data="data[3]" style="grid-column:1; grid-row:2;"></crime-box>
      <crime-box class="box" :data="data[4]" style="grid-column:2; grid-row:2;"></crime-box>
      <crime-box class="box" :data="data[5]" style="grid-column:3; grid-row:2;"></crime-box>
    </div>
</template>


