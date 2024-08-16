<script setup>
import {ref} from 'vue'

const props = defineProps(['data'])
let finData = ref({id:"Loading ID",case_number:"Loading Case Number",date:"Loading",block:"Loading Block",iucr:"Loading IUCR",primary_type:"Loading Primary Type",description:"Loading Description",location_description:"Loading Location Description",arrest:false,domestic:false,beat:"Loading Beat",district:"Loading District",ward:"Loading Ward",community_area:"Loading Community Area",fbi_code:"Loading FBI Code",year:"Loading Year",updated_on:"Loading Last Update"})
if (typeof props.data == "string") {
}
else {
  finData.value = props.data
}

</script>

<template>
  <div class="crime">
    <h1>{{finData.primary_type}}</h1>
    <h2>{{finData.description}}</h2>
    <p>{{finData.location_description}}</p>
    <p>Date: {{finData.date.slice(0,10)}}</p>
  </div>

</template>

<style>
.crime {
  border: 5px solid rgba(255,210,255,1);
  border-radius: 10px;
  margin: 10px;
  background: rgba(255,220,255,1);
  padding: 5%
}
</style>