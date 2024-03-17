<template>
  <ul>
    <li v-for="item in userList" :key="item.id">
      {{ item.name +'---'+ item.age}}
    </li>
  </ul>
</template>

<script setup>
import axios from "axios";
import { onMounted, ref } from "vue";
const userList = ref([])
onMounted(() => {
  axios.get("http://localhost:3000/").then((res) => {
    userList.value = res.data
  })
})
</script>

<style lang="scss" scoped>

</style>