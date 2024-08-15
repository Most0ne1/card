<template>
  <div>
 
   <ProductDetails :product="product"/>
  </div>
</template>

<script setup>

// Get the product ID from the route parameters
const { id } = useRoute().params
const uri = `https://fakestoreapi.com/products/${id}`

// Fetch the specific product
const { data: product } = await useFetch(uri,{key:id})

// Set the page meta with the correct layout
definePageMeta({
  layout: 'products' // Assuming the layout should be named 'products'
})
</script>

