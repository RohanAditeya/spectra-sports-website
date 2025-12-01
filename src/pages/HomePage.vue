<script setup lang="ts">
    import PageHeader from '@/components/PageHeader.vue';
    import backgroundImgUrl from '../static/006.jpg';
    import { Icon } from '@iconify/vue'
</script>

<template>
    <PageHeader/>
    <main :style="{ '--bg': `url(${backgroundImgUrl})` }" :class="['main-section']">
        <section :class="['tag-section']">
            <div :class="['tag-container']">
                <h1 :class="['welcome']">Welcome to Spectra</h1>
                <p>We are team of talanted designers making websites with Bootstrap</p>
                <div :class="['get-started-container']">
                    <span :class="['get-started-icon']">
                        <Icon icon="material-symbols:line-end-arrow" width="15" height="15"  style="color: #fff" />
                    </span>
                    <span :class="['get-started-message']">Get Started</span>
                </div>
            </div>
        </section>
    </main>
</template>

<style lang="css" scoped>

    .tag-section {
        background: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.4)), var(--bg);
        background-attachment: fixed;
        background-size: cover;
        background-position: center center;
        height: 70vh;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .tag-section div {
        background: none;
        color: #ffffff;
        width: 70%
    }

    .welcome {
        font-size: 3em;
        margin: 0;
    }

    .tag-container p {
        font-size: 1.25em;
        margin: 0;
        margin-bottom: 25px;
    }

    .get-started-icon {
        background-color: var(--spectra-red);
        padding: 15px;
        border-radius: 100% 100% 100% 100%;
        position: relative;
        z-index: 5;
    }

    .get-started-message {
        background-color: #172c42;
        padding: 10px 20px;
        position: relative;
        margin-left: -10px;
        z-index: 4;
        border-radius: 0% 50px 50px 0%;
    }
</style>