<template>
    <div class='grid grid-cols-4 gap-2 mb-4'>
        <div class="m-2" v-for='item in products'>
           <ProductCard :product="item"/>
        </div>
    </div>
</template>

<script setup>

// Fetch Products
const { data:products } = await useFetch('https://fakestoreapi.com/products')

</script>