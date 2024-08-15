<template>
  <div>
    <div class="grid grid-cols-4 gap-5">
      <!-- Iterate through products and create a link for each product -->
      <div v-for="p in products" :key="p.id">
      
        <ProductCard  :product="p"/>
     
      </div>
    </div>
  </div>
</template>

<script setup>
// Set the page meta with a custom layout
definePageMeta({
  layout: 'products' // Fixed typo in layout name
})

// Fetch products from the API
const { data: products } = await useFetch('https://fakestoreapi.com/products')
</script>

<style scoped>
/* Add your custom styles here */
</style>
