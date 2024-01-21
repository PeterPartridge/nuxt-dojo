<template>
    <div>
       <div class="grid grid-cols-4 gap-5">
        <div v-for="product in products">
            <NuxtLink :to="`/products/${product.id}`">{{ product.title }}</NuxtLink>
        </div>
       </div>
    </div>
</template>
<script setup>
definePageMeta({
    layout: 'products'
})

const {data: products } = await useFetch('https://fakestoreapi.com/products')

</script>
<style>
h2 {
    margin-bottom: 20px;
    font-size: 20px;
}
</style>