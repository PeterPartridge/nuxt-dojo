<template>
    <div>
        <h2>{{ product.title }}</h2>
        <p>{{product.price}}</p>
    </div>
</template>
<script setup>

const { id } = useRoute().params
const url = 'https://fakestoreapi.com/products/'+ id

const {data:product} = await useFetch(url, {key:id});

definePageMeta({
    layout: 'products'
})
</script>
<style scoped>
h2 {
    margin-bottom: 20px;
    font-size: 20px;
}
</style>