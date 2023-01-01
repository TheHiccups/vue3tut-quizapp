<script setup>
    import {defineProps} from "vue";

    const {quiz} = defineProps(['quiz']);
</script>

<template>
    <!-- <div class="card">
        <img src="https://images.unsplash.com/photo-1518133910546-b6c2fb7d79e3?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80" alt=""/>
        <div class="card-body" >
            <h2>Math</h2>
            <p>3 questions</p>
        </div>
    </div> -->
    <div class="card">
        <img :src="quiz.img" alt=""/>
        <div class="card-body" >
            <h2>{{quiz.name}}</h2>
            <p>{{quiz.questions.length}} questions</p>
        </div>
    </div>
</template>

<style scoped>
    .card{
        width: 310px;
        margin-bottom: 35px;
        margin-right: 20px;
        overflow:hidden;
        cursor: pointer;

        border-radius: 2%;
        box-shadow: 1px 1px 10px #0000001a;
    }
    .card img{
        width: 100%;
        height: 190px;
        margin: 0;
    }
    .card-body{
        padding: 0 10px;
    }
    .card h2{
        font-weight: bolder;
    }
    .card p{
        text-align: right;
    }
</style>