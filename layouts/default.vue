<!--以default作為預設 => <NuxtLayout/>-->
<template>
  <div class="bg-sky-100 py-6">
    <div class="flex items-center justify-end">
      <NuxtLink to="/" class="flex items-center justify-end">
        <button
          class="radius-2xl mx-2 mt-1 rounded-lg bg-purple-600 px-4 py-2 font-semibold text-white hover:bg-purple-800"
        >
          首頁
        </button>
      </NuxtLink>
    </div>
    <p class="px-6 py-2 text-2xl text-sky-600">
      這個藍色的背景是預設的布局，預計給全部的頁面做使用
    </p>

    <slot name="header" />
    <slot />
    <!-- 插槽 -->
    <slot name="footer" />
  </div>
</template>
