<template>
    <div class=' p-3 rounded-md bg-white shadow-lg h-full text-center border'>
        <div class='relative'>
        <img :src="product.image" alt='product thumb' class='thumb '>
        <p class='absolute top-0 right-0 bg-green-500 text-white text-sm rounded-full px-2 py-1 capitalize'>{{product.category}}</p>
        </div>
        <p class='font-bold text-gray-500 m-4 truncate'>{{product.title}}</p>
        <p class='font-bold text-gray-500 m-4 truncate'>Rating: {{product.rating.rate}}</p>
        <NuxtLink :to="`/products/${product.id}`">
            <PrimaryButton>View Details</PrimaryButton>
        </NuxtLink>
    </div>
</template>

<script setup>
const { product } = defineProps(['product'])
</script>

<style scoped>
.thumb {
    max-height:120px;
    max-width:70%;
    margin: 0 auto;
}
</style>