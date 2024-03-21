<template>
    <section class="featured-products-wrapper">
        <h2> Our featured products </h2>
        <Splide class="slider-wrapper" :options="options" :has-track="false">
            <SplideTrack class="splide-track-wrapper">
                <SplideSlide class="product">

                </SplideSlide>
            </SplideTrack>

            <div class="splide__arrows">
                <button class="splide__arrow splide__arrow--prev">
                    <img src="../assets/LeftArrow.svg">
                </button>
                <button class="splide__arrow splide__arrow--next">
                    <img src="../assets/RightArrow.svg">
                </button>
            </div>

            <div class="splide__progress">
                <div class="splide__progress__bar" />
            </div>
        </Splide>
    </section>
</template>

<script lang="ts">
import { Splide, SplideSlide, SplideTrack } from '@splidejs/vue-splide';
import { defineComponent } from 'vue';


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
            height: '15rem',
            width: '80vw',
            perMove: 1,
            focus: 'center',
            pagination: true,
        };

        return { options };
    },

});
</script>


<style lang="scss">
@import '@splidejs/vue-splide/css/skyblue';
@import "../scss/components/_featuredProducts.scss"
</style>