<template>
  <div>
    <p class="my-2 px-2 text-2xl text-gray-700">這裡是最外層 app.vue</p>
    <NuxtLayout>
      <template #header>
        <p class="px-12 text-green-500">這段文字會顯示 header 插槽</p>
      </template>
      <template #default>
        <p class="px-12 py-6 text-xl text-rose-500">
          被 NuxtLayout 包裹的元件將會放置到 Layout 的預設 slot 插槽中
        </p>
      </template>
      <template #footer>
        <p class="px-12 text-sky-500">這段文字會顯示 footer 插槽</p>
      </template>
    </NuxtLayout>
    <div class="flex items-center justify-between">
      <div class="flex items-center">
        <CustomHelloBinhan />
        <h1 class="ml-2 text-5xl font-semibold text-purple-600">
          {{ title }}
        </h1>
      </div>
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
