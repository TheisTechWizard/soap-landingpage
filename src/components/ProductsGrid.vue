<template>
    <section id="products" class="products-wrapper">
        <h2>Products</h2>
        <div class="products-grid">
            <div class="product" v-for="product in products " :key="product.id">
                <img :src="product.img" alt="product picture">
                <h3>{{ product.name }}</h3>
                <p>{{ product.descr }}</p>
                <button> Buy now! </button>
            </div>
        </div>
    </section>
</template>

<script lang="ts">
import axios from 'axios';

export default {

    data() {
        return {
            products: [{
                id: Number,
                img: String,
                name: String,
                descr: String
            }]
        };
    },

    mounted() {
        axios.get('/src/dummyData/Products.json').then(response => {
            this.products = response.data
        })
    }
}
</script>


<style lang="scss">
@import "../scss/components/productsGrid"
</style>