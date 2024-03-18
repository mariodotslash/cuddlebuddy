<template>
    <div class=' card'>
        <div class='grid grid-cols-2 gap-8'>
            <div class='p-6'>
                <img :src="product.image" alt='product thumb' class='mx-auto'>
            </div>
            <div class='p-6'>
                <h2 class='font-bold text-gray-500 m-4 truncate text-4xl'>{{product.title}}</h2>
                <p class='font-bold text-gray-500 m-4 truncate'>Price: R{{product.price}}</p>
                <h3 class='font-bold '>Product Description:</h3>
                <p class=''>{{product.description}}</p>
            </div>
        </div>
      
        <!-- <p class='font-bold text-gray-500 m-4 truncate'>{{product.title}}</p>
        <NuxtLink :to="`/products/${product.id}`">
            <PrimaryButton>View Details</PrimaryButton>
        </NuxtLink> -->
    </div>
</template>

<script setup>
const { product } = defineProps(['product'])
</script>

<style scoped>

</style>