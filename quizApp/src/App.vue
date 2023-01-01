<script setup>
  import q from "./data/quizes.json";
  import {ref, watch} from "vue";
  import Card from "./components/Card.vue";

  const quizes = ref(q);
  const search = ref("");

  watch(search, () => {
    quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()));
  })

</script>
<!-- ======================================================================================================================================= -->
<template>
  <main>
    <div class="container">

      <header>
        <h1>Quizes</h1>
        <input v-model.trim="search" type="text" placeholder="Search..." />
        <button class="btn-clear" @click="search=''">x</button>
      </header>

      <div class="card-container">
        <Card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz"/>
      </div>

    </div>
  </main>
</template>
<!-- ======================================================================================================================================= -->
<style scoped>
  .container {
    max-width: 1000px;
    margin: 0 auto;
    padding-left: 20px;
  }
  header{
    margin: 30px 0 10px 0;
    display:flex;
    align-items: center;
  }
  header h1{
    font-weight: bold;
    margin-right: 30px;
  }
  header input{
    width: 200px;
    border: none;
    border-radius: 5px;
    background-color: #aaaaaa1a;
    /* opacity: 0.1; */
    padding: 10px;
    color: #000000ff;
  }
  header .btn-clear{
    margin-left:5px;
    border: none;
    font-weight: bold;
    background-color: #fff;
  }
  .btn-clear:hover{
    font-size: 1.2rem;
    color: red;
    margin-left: 4px;
  }

  .card-container{
    display: flex;
    flex-wrap: wrap;
    margin-top: 40px;
  }
  
  
</style>
