<script setup>
  import {useRoute, RouterView} from 'vue-router'
  import {ref, onBeforeMount} from "vue"
  import cars from "../data.json"

  const car = ref(null)
  const route = useRoute()
  const {id} = route.params
  onBeforeMount(() => {
    car.value = cars.find(c => c.id === parseInt(id))
  })
 
</script>
<template>
    <div class="container">
        <div v-if="car" class="total">
          <div class="img">
            <img :src="car.img" alt="">
          </div>
          <div class="info">
            <h1>The car</h1>
            <p>Make: {{ car.make }}</p>
            <p>Body: {{ car.body }}</p>
            <p>Price: {{ car.price }}</p>
            <p>Year: {{ car.year }}</p>
          </div>
          <RouterView />
        </div>
        
        <div v-else>
          <h1>Car Not Found</h1>
        </div>
    </div>
</template>

<style scoped>

.total {
  display:flex;
  align-items: center;
  flex-direction: row;
  justify-content: space-around;
  max-width: 1000px;
  height: 400px;

  background-color: #7A7C94
}
.img{
  width: 300px;
  height: 200px;
}
img{
  width: 400px;
  height: 300px;
}
.info{
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}
p{
  color: white;
  font-size: 20px;
}
</style>