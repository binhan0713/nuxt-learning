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
    <ClientAndServer /><!-- SSR to SCR-->
    <JustClient /><!-- 檔名多加.client 只有在Client才會渲染，跟ClientOnly差不多 -->
    <ClientOnly>
      <template #fallback
        ><!-- SSR時顯示 -->
        <p class="my-6 flex justify-center">
          [BaseApplyButton.vue] 元件載入中...
        </p></template
      >
      <p class="px-12 py-6 text-xl text-rose-500">
        這段文字只會在瀏覽器中顯示(CSR)，不會在 SSR 時顯示
      </p>
      <BaseApplyButton />
    </ClientOnly>
    <div class="mt-8 flex items-center">
      <input id="show-button" v-model="show" type="checkbox" class="h-5 w-5" />
      <label for="show-button" class="ml-2 block text-base text-slate-800"
        >顯示報名按鈕</label
      >
    </div>
    <LazyBaseApplyRoundButton v-if="show" /><!-- 需要時才載入component -->
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
    <IronManWelcome />

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
const show = ref(false)
const name = 'ㄅㄏ'
const title = `${name}帥哥`
useHead({
  title: 'ㄅㄏ帥哥',
  meta: [
    {
      hid: 'description',
      name: 'description',
      content: '這是一個帥哥的網站'
    }
  ]
})
</script>

<style scoped></style>
