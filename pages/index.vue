<template>
  <div>
    <div class="flex items-center justify-between">
      <div class="flex items-center">
        <CustomHelloBinhan />
        <h1 class="ml-2 text-5xl font-semibold text-purple-600">
          {{ title }}
        </h1>
      </div>
      <GoHome />
    </div>
    <div class="flex items-center">
      <CurryAvatar />
      <NuxtLink
        to="/category"
        class="ml-4 text-lg font-semibold text-purple-600 hover:text-purple-800"
      >
        探索動態路由的秘密
      </NuxtLink>
    </div>
    <hr class="mx-auto mb-4 border-2 border-gray-300" />
    <NuxtLink
      to="/about"
      class="font-semibold text-purple-600 hover:text-purple-800"
    >
      <span class="border-b-2 border-purple-600 hover:border-purple-800"
        >關於我</span
      >
    </NuxtLink>
    <NuxtLink
      to="/contact"
      class="ml-4 font-semibold text-purple-600 hover:text-purple-800"
    >
      <span class="border-b-2 border-purple-600 hover:border-purple-800"
        >聯絡我</span
      >
    </NuxtLink>
  </div>
</template>

<script setup>
const name = 'ㄅㄏ'
const title = `${name}帥哥`
onMounted(() => {
  document.title = 'ㄅㄏ帥哥'
})
</script>

<style scoped></style>
