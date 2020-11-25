<template>
  <div>
    <p>Basic Computed Playground with Compostin API</p>

    <input type="checkbox" v-model="status" value="status" /> 
    SET : {{ message }}
    <p>SET : {{ isCheck }}</p>
    <p> {{ status }} </p>
    <hr />
  </div>
</template>
<script>

import { ref, computed } from '@vue/composition-api'
export default {
  name: "ComputedCompostionAPI",
  setup() {
    const isCheck = ref(true);
    const message = ref("Composition API");
    const status = computed({
      get: () => {
        console.log(`Computed isCheck value is ${isCheck.value}`)
        return`GET : Computed isCheck value is ${isCheck.value}`
      },
      set: val => {
        isCheck.value = val
        isCheck.value ? message.value = 'Checked' : message.value = 'Uncheck'
        console.log(val, message.value)
      }
    })
     return {
       isCheck,
       status,
       message
  }
  },
 
};
</script>
