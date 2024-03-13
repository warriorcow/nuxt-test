<template>
  <div>
    <button @click="getData">fetchData</button>
    <div>{{ dataPosts }}</div>
  </div>
</template>

<script setup lang="ts">

const dataPosts = ref(null)
async function getData() {
  const { data } = await useAsyncData(
    'mountains',
    () => $fetch('https://retoolapi.dev/WkceUB/data')
  )

  dataPosts.value = data;
}


</script>
