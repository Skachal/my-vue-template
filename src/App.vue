<script setup>
import Header from './components/HeaderComponent.vue'
import { ref, provide } from 'vue'
import Drawer from './components/DrawerComponent.vue'

const openCart = ref(false)
const openDrawer = () => {
  openCart.value = true
}

const closeDrawer = () => {
  openCart.value = false
}
provide('closeDrawer', closeDrawer)
</script>

<template>
  <Drawer v-if="openCart" />
  <div class="w-4/5 m-auto bg-white rounded-xl shadow-xl mt-14 pb-2">
    <Header :openDrawer="openDrawer" />
    <div class="p-10">
      <router-view></router-view>
    </div>
  </div>
</template>

<style scoped>
</style>
