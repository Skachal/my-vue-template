<template>
  <header class="flex justify-between border-b border-slate-300 px-10 py-5">
    <router-link to="/">
      <div class="flex gap-4 items-center">
        <img class="w-10" :src="`${baseUrl}logo.png`" alt="Logo" />
        <div>
          <h2 class="text-xl font-bold uppercase">Vue Sneakers</h2>
          <p class="text-slate-400">Магазин лучших кроссовок</p>
        </div>
      </div>
    </router-link>
    <ul class="flex items-center gap-10">
      <li
        @click="openDrawer"
        class="flex items-center gap-3 cursor-pointer text-gray-500 hover:text-black"
      >
        <img :src="`${baseUrl}cart.svg`" alt="Cart" />
        <b>1205 тенге.</b>
      </li>
      <router-link to="/favorites">
        <li class="flex items-center gap-3 cursor-pointer text-gray-500 hover:text-black">
          <img :src="`${baseUrl}heart.svg`" alt="Favorites" />
          <span>Закладки</span>
        </li>
      </router-link>
      <li class="flex items-center gap-3 cursor-pointer text-gray-500 hover:text-black">
        <img :src="`${baseUrl}profile.svg`" alt="Profile" />
        <span>Профиль</span>
      </li>
    </ul>
  </header>
</template>

<script setup>
defineProps({
  openDrawer: Function
})

// Define base URL for assets
const baseUrl = import.meta.env.BASE_URL || '/'
</script>
