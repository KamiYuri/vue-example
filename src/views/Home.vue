<template>
  <h1>{{ data }}</h1>
  <el-button type="primary" icon="Menu">Submit</el-button>
</template>

<script setup>
import axios from "@/request/axios.js";
import { ref } from "vue";

const data = ref("");

const getData = async () => {
  axios.get("/test").then((request) => {
    console.log(request);
    data.value = request.data;
  });
};

getData();
</script>

<style scoped></style>
