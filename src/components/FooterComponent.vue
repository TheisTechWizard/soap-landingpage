<template>
    <section class="footer-section">
        <div class="soMe-links">
            <a href="https://www.linkedin.com/in/theishaahr/">
                <img src="..\assets\LinkedIn Logo.png" alt="LinkedIn Logo">
            </a>
            <a href="https://github.com/TheisTechWizard/soap-landingpage">
                <img src="../assets/GitHub Logo-white.png" alt="GitHub Logo" />
            </a>
        </div>
        <div class="contact-info">
            <p>Theis Nielsen Haahr • theishaahr@gmail.com • 71708705</p>
        </div>
        <ol class="footer-links">
            <a @click="scrollTo('hero')">Home</a>
            <a @click="scrollTo('featured')">Featured</a>
            <a @click="scrollTo('about')">About</a>
            <a @click="scrollTo('products')">Products</a>
            <a @click="scrollTo('benefits')">Benefits</a>
            <a @click="scrollTo('contact')">Contact</a>
        </ol>
    </section>
</template>

<script lang="ts">
export default {
    methods: {
        scrollTo(sectionId: string): void {
            const section = document.getElementById(sectionId);
            if (section) {
                window.scrollTo({
                    top: section.offsetTop - 50,
                    behavior: 'smooth',
                });
            }
        },
    }
}
</script>


<style lang="scss">
@import "../scss/components/_footerComponent.scss"
</style>