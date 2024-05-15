<template>
    <section class="main-navbar-wrapper">
        <div class="left-items">
            <div class="logo-wrapper">
                <img src="../assets/Logo.PNG">
            </div>
            <ol class="navbar-links">
                <a @click="scrollTo('hero')">Home</a>
                <a @click="scrollTo('featured')">Featured</a>
                <a @click="scrollTo('about')">About</a>
                <a @click="scrollTo('products')">Products</a>
                <a @click="scrollTo('benefits')">Benefits</a>
                <a @click="scrollTo('contact')">Contact</a>
            </ol>
        </div>
        <div class="burger-menu">
            <img class="burger-icon" src="../assets/burger-menu.png" alt="burger menu" @click="toggleMenu">
            <ul class="menu" :class="{ 'active': menuOpen }">
                <a @click="scrollTo('hero')">Home</a>
                <a @click="scrollTo('featured')">Featured</a>
                <a @click="scrollTo('about')">About</a>
                <a @click="scrollTo('products')">Products</a>
                <a @click="scrollTo('benefits')">Benefits</a>
                <a @click="scrollTo('contact')">Contact</a>
            </ul>
        </div>
        <button class="big-screen-btn">Shop Now</button>
    </section>
</template>


<script lang="ts">
export default {

    data() {
        return {
            menuOpen: false
        };
    },

    methods: {
        scrollTo(sectionId: string): void {
            const section = document.getElementById(sectionId);
            if (section) {
                window.scrollTo({
                    top: section.offsetTop - 50,
                    behavior: 'smooth',
                });

                this.toggleMenu()
            }
        },

        toggleMenu() {
            this.menuOpen = !this.menuOpen;
        }
    }
}
</script>

<style lang="scss">
@import "../scss/components/_mainNavbar.scss"
</style>