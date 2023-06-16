<script setup>
import workflow from './workflow/workflow.vue'
import {ref} from "vue";
let data=ref({})

const ok = (data1) => {
    console.log(data1)
}



</script>

<template>


  <div id="app">
    <workflow
        :data="data"
        @ok="ok"
    />
  </div>

</template>

<style >
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
