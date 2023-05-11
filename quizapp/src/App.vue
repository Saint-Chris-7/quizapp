<script setup>
  import { ref, watch } from "vue";
  import q from "./data/quize.json"
  import Card from "./components/Card.vue"

  const quizzes = ref(q)
  const search = ref("")

  watch(search,() =>{
    quizzes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()))
  })
</script>

<template>
  <div class="container">
    <header>
      <h1>Quizzes</h1>
      <input type="text" name="" v-model.trim="search" id="" placeholder="search...">
    </header>
    <div class="options-container">
      <Card v-for="quiz in quizzes" :key="quiz.id" :quiz="quiz"/>
      <!-- <div class="card" v-for="quiz in quizzes" :key="quiz.id">
        <img :src="quiz.img" alt="">
        <div class="card-text">
          <h2>{{ quiz.name }}</h2>
          <p>{{ quiz.questions.length }} questions</p>
        </div>
      </div> -->
    </div>
  </div>
</template>
<style scoped>
.container{
  max-width: 90%;
  margin: auto;
}
header{
  margin: 30px 0 10px;
  display: flex;
  align-items: center;
}
header h1{
  font-weight: bold;
  margin-right: 30px;
}
header input{
  border: none;
  background-color: rgba(0,0,0, .4);
  padding: 10px;
  border-radius: 10px;
}
.options-container{
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}
/* card */

</style>