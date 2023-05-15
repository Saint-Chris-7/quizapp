<script setup>
  import { useRoute, useRouter, RouterView } from 'vue-router'; //useroute enables use to get information from the url that we are in
  import cars from "../data/car.json"

  const route = useRoute()
  const router = useRouter()//mutate and adjust page
  // const car = cars.find(c => c.id === parseInt(route.params.id))
  const cardId = parseInt(route.params.id)

  const car = cars.find(c => c.id === cardId)
  

</script>

<template>
    <div v-if="car">
        <h1>Car View</h1>
        <p>{{ car.name }}</p>
        <p>{{ car.price }}</p>
        <p>{{ car.year }}</p>
        <button @click="router.push(`/car/${cardId}/contact`)">Contact</button>
        <RouterView/>
    </div>
    <div v-else>
      <h1>car not found</h1>
    </div>

</template>