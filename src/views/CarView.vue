<script setup>
  import {useRoute} from 'vue-router'
  import {ref, onBeforeMount} from "vue"
  import cars from "../data.json"
  const route = useRoute()

  onBeforeMount(() => {
    const carData = cars.find(c => c.id === parseInt(id))
  })
  const {id} = route.params
</script>
<template>
    <div class="container">
        <h1>The car</h1>
    </div>
</template>