<template>
  <h2 class="font-bold text-xl">Мои закладки</h2>
  <CardList :items="items" />
</template>

<script setup>
import CardList from '../components/CardsItems.vue'
import axios from 'axios'
import { onMounted, ref } from 'vue'

const items = ref([])

const fetchFavorites = async () => {
  try {
    const { data } = await axios.get('https://269b3b45e08bcd1a.mokky.dev/items')
    const { data: favorites } = await axios.get('https://269b3b45e08bcd1a.mokky.dev/favorites')

    items.value = data.filter((item) => favorites.find((fav) => fav.sneakerId === item.id))

    console.log(items.value)
  } catch (error) {
    console.log(error)
  }
}

onMounted(fetchFavorites)
</script>
