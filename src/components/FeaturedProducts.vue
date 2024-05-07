<template>
    <section id="featured" class="featured-products-wrapper">
        <h2>featured products</h2>
        <Splide class="slider-wrapper" :options="options" :has-track="false">
            <SplideTrack class="splide-track-wrapper">
                <SplideSlide class="product" v-for="product in featuredProducts" :key="product.id">
                    <img :src="product.img" alt="">
                    <h3> {{ product.name }}</h3>
                    <p> {{ product.descr }}</p>
                    <button> View details </button>
                </SplideSlide>
            </SplideTrack>

            <div class="splide__arrows">
                <button class="splide__arrow splide__arrow--prev">
                    <svg width="22" height="38" viewBox="0 0 22 38" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M20.768 20.7678C21.7443 19.7915 21.7443 18.2085 20.768 17.2322L4.85809 1.32233C3.88178 0.346021 2.29886 0.346021 1.32255 1.32233C0.346243 2.29864 0.346243 3.88155 1.32255 4.85787L15.4647 19L1.32255 33.1421C0.346243 34.1184 0.346243 35.7014 1.32255 36.6777C2.29886 37.654 3.88178 37.654 4.85809 36.6777L20.768 20.7678ZM19.0001 21.5H19.0002V16.5H19.0001V21.5Z"
                            fill="white" />
                    </svg>
                </button>
                <button class="splide__arrow splide__arrow--next">
                    <svg width="22" height="38" viewBox="0 0 22 38" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M20.768 20.7678C21.7443 19.7915 21.7443 18.2085 20.768 17.2322L4.85809 1.32233C3.88178 0.346021 2.29886 0.346021 1.32255 1.32233C0.346243 2.29864 0.346243 3.88155 1.32255 4.85787L15.4647 19L1.32255 33.1421C0.346243 34.1184 0.346243 35.7014 1.32255 36.6777C2.29886 37.654 3.88178 37.654 4.85809 36.6777L20.768 20.7678ZM19.0001 21.5H19.0002V16.5H19.0001V21.5Z"
                            fill="white" />
                    </svg>
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
            height: '29rem',
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
        axios.get('/src/dummyData/Products.json').then(response => {
            const firstFourItems = response.data.slice(0, 4);
            this.featuredProducts = firstFourItems;
        })
    }

});
</script>


<style lang="scss">
@import '@splidejs/vue-splide/css/skyblue';
@import "../scss/components/_featuredProducts.scss"
</style>