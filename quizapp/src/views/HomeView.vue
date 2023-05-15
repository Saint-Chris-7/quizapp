<script setup>
  import { RouterLink } from 'vue-router';
  import cars from '../data/car.json'
  
</script>

<template>
    <div>
        <h1>Home page</h1>
        <div class="cars">
            <RouterLink :to="`car/${car.id}`" v-for="car in cars" :key="car.id" href="">{{ car.name }}</RouterLink>
        </div>
    </div>
</template>

<style scoped>
  .cars{
    display: flex;
  }
  .cars a{
    text-decoration: none;
    color: black;
    width: 100%;
    box-shadow: 1px 1px 10px black;
    margin: 10px;
  }
</style>