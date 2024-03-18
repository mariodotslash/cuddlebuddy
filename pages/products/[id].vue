<template>
    <div>
        <ProductDetails :product='product'/>
       
    </div>
</template>

<script setup>
const { id } = useRoute().params
const uri = 'https://fakestoreapi.com/products/'+ id

//fetch product
const { data:product } = await useFetch(uri, {key:id})

</script>

<style scoped>
.thumb {
    max-height:120px;
    max-width:70%;
    margin: 0 auto;
}
</style>