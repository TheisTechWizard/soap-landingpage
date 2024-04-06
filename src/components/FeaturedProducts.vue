<template>
    <section class="featured-products-wrapper">
        <h2>featured products</h2>
        <Splide class="slider-wrapper" :options="options" :has-track="false">
            <SplideTrack class="splide-track-wrapper">
                <SplideSlide class="product" v-for="product in featuredProducts" :key="product.id">
                    <img :src="product.img" alt="Product Image">
                    <h3> {{ product.name }}</h3>
                    <p> {{ product.descr }}</p>
                    <button> View details </button>
                </SplideSlide>
            </SplideTrack>

            <div class="splide__arrows">
                <button class="splide__arrow splide__arrow--prev">
                    <img src="../assets/ArrowLeft.svg">
                </button>
                <button class="splide__arrow splide__arrow--next">
                    <img src="../assets/ArrowRight.svg">
                </button>
            </div>
        </Splide>
    </section>
</template>

<script lang="ts">
import { Splide, SplideSlide, SplideTrack } from '@splidejs/vue-splide';
import { defineComponent } from 'vue';
import axios from 'axios';


export default defineComponent({
    components: {
        Splide,
        SplideSlide,
        SplideTrack,
    },

    setup() {
        const options = {
            type: 'loop',
            perPage: 3,
            gap: '15px',
            height: '28rem',
            width: '85vw',
            perMove: 1,
            focus: 'center',
            drag: false,
        };

        return { options };
    },

    data() {
        return {
            featuredProducts: [{
                id: Number,
                img: String,
                name: String,
                descr: String
            }]
        };
    },

    mounted() {
        axios.get('/src/dummyData/featuredProducts.json').then(response => { this.featuredProducts = response.data; })
    }

});
</script>


<style lang="scss">
@import '@splidejs/vue-splide/css/skyblue';
@import "../scss/components/_featuredProducts.scss"
</style>