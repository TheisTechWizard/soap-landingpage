<template>
    <section class="main-navbar-wrapper">
        <div class="left-items">
            <div class="logo-wrapper">
                <img src="../assets/Logo.PNG">
            </div>
            <ol class="left-item-list">
                <a @click="scrollTo('hero')">Home</a>
                <a @click="scrollTo('featured')">Featured</a>
                <a @click="scrollTo('about')">About</a>
                <a @click="scrollTo('products')">Products</a>
                <a @click="scrollTo('benefits')">Benefits</a>
                <a @click="scrollTo('contact')">Contact</a>
            </ol>
        </div>
        <div class="right-items">
            <ul class="right-item-list">
                <button>Shop Now</button>
            </ul>
        </div>
    </section>
</template>


<script lang="ts">
export default {
    methods: {
        scrollTo(sectionId: string): void {
            const section = document.getElementById(sectionId);
            if (section) {
                window.scrollTo({
                    top: section.offsetTop,
                    behavior: 'smooth',
                });
            }
        }
    }
}
</script>

<style lang="scss">
@import "../scss/components/_mainNavbar.scss"
</style>