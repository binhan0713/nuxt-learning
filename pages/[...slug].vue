<template>
  <div class="bg-white py-24">
    <div class="flex flex-col items-center">
      <h1 class="text-8xl font-semibold text-red-500">404</h1>
      <p class="my-8 text-3xl text-gray-800">Not Found</p>
      <p class="my-8 text-xl text-gray-800">真的是找不到這個頁面啦 😓</p>
      <p class="my-8 text-xl text-gray-800">{{ slug }}</p>
    </div>
  </div>
</template>

<script setup>
// 如果沒有那個頁面，會導入這裡
// 但是如果有那個頁面，那就會導入那個頁面(其優先級較高)
const route = useRoute()
const { slug } = route.params
setResponseStatus(404) // 設定狀態碼
</script>
