<template>
    <section id="about" class="about-us-wrapper">
        <div ref="fadeElement" class="left-side">
            <h2>About us</h2>
            <transition>
                <p v-if="isVisible">
                    We here at [Insert Company Name] are passionate about crafting high-quality, luxurious soap bars
                    that
                    elevate your everyday bathing experience. Our journey began with a simple desire to create soap
                    products
                    that not only cleanse but also nourish and pamper your skin.
                </p>
            </transition>
            <transition>
                <p v-if="isVisible">
                    At [Insert Company Name], we believe in the power of natural ingredients. That's why each of our
                    soap
                    bars
                    is
                    meticulously handcrafted using only the finest botanicals, essential oils, and moisturizing agents.
                    From
                    soothing lavender to invigorating citrus, every scent is carefully selected to transport you to a
                    world
                    of
                    indulgence and relaxation.
                </p>
            </transition>
            <transition>
                <p v-if="isVisible">
                    But it's not just about what goes into our products—it's also about what we leave out. You won't
                    find
                    any
                    harsh chemicals, artificial fragrances, or additives in our soap bars. We're committed to creating
                    gentle,
                    cruelty-free formulas that are safe for you and the planet.
                </p>
            </transition>
            <transition>
                <p v-if="isVisible">
                    Whether you're unwinding after a long day or starting your morning off right, [Insert Company Name]
                    has
                    the
                    perfect soap bar for every occasion. Our goal is simple: to provide you with a luxurious bathing
                    experience
                    that leaves you feeling refreshed, rejuvenated, and ready to take on the day.
                </p>
            </transition>
            <transition>
                <p class="disclaimer" v-if="isVisible">
                    Disclaimer: Please note that [Insert Company Name] is a fictional company created solely for fun and
                    portfolio purposes. The products and services described on this website are not real, and any
                    resemblance to actual products or companies is purely coincidental. Please don't sue me.
                </p>
            </transition>
        </div>
        <div class="right-side">
            <img src="" alt="Some picture">
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            isVisible: false,
        }
    },

    mounted() {
        // Intersection Observer setup
        const observer = new IntersectionObserver(entries => {
            entries.forEach(entry => {
                if (entry.isIntersecting && entry.intersectionRatio >= 0.3) {
                    this.isVisible = true;
                    observer.unobserve(entry.target);
                }
            });
        }, { threshold: 0.3 });

        // Start observing the target element
        observer.observe(this.$refs.fadeElement);
    },
};
</script>


<style lang="scss">
@import "../scss/components/_aboutUs.scss"
</style>