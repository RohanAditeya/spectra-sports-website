<script setup lang="ts">
    import PageHeader from '@/components/PageHeader.vue'
    import backgroundImgUrl from '../static/006.jpg'
    import servicesUrl from '../static/services.png'
    import { Icon } from '@iconify/vue'
    import DisplayCard from '@/components/DisplayCard.vue'
    import serviceCards from "../data/serviceCard.json" with { type: "json" }
    import clientsOnboarded from "../data/clients-number.json" with { type: "json" }
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
        <section :class="['services-section']">
            <DisplayCard v-for="(serviceCard, index) in serviceCards" :card-header="serviceCard.cardHeader" :card-description="serviceCard.cardDescription" :key="index" :icon-name="serviceCard.iconName" :is-position-relative="true" :is-width-fractional="true"/>
        </section>
        <section :class="['onboarded-clients-section']">
            <span v-for="(client, index) of clientsOnboarded" :key="index" :class="['onboarded-client-container']">
                <h1>{{ client.onboardedCount }}</h1>
                <p>{{ client.clientType }}</p>
            </span>
        </section>
        <section :class="['call-to-action-section']">
            <div :class="['call-to-action-description-container']">
                <h2>Call To Action</h2>
                <p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
            </div>
            <button>Call To Action</button>
        </section>
        <section :class="['our-aim-section']">
            <div :class="['our-aim-container']">
                <h2>Our Aim</h2>
                <p>
                    Spectra Sports aim to build a strong and powerful community that aligns with our values of constantly driving forward with passion, commitment and ambition. We strive to make meaningful and lasting connections amongst players, mentors, coaches, and other sports-related personnel to make it a go-to platform for complete sports assistance.
                </p>
            </div>
            <div :class="['our-aim-parent-cards-containers']">
                <div :class="['our-aim-cards-containers']">
                    <DisplayCard :class="['our-aim-cards']" :card-header="'Vision Statement'" :card-description="'Our vision is to build a global scale sports assistance platform by providing our very best services in the most practical and functional way to any dreamer from across the world.'" :icon-name="'mdi:contract-outline'"/>
                    <DisplayCard :class="['our-aim-cards']" :card-header="'Mission Statement'" :card-description="'Our mission is to achieve hand in hand with our dreamers and quench the thirst of success and glory through our holistic step by step assistance. '" :icon-name="'ph:speedometer-light'"/>
                </div>
                <div :class="['services-image-container']">
                    <img :src="servicesUrl" alt="Image showing support through means of services to user" :class="['services-image']"/>
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

    .services-section {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
        background-color: #fbfbfb;
    }

    .onboarded-clients-section {
        display: flex;
        justify-content: space-around;
        flex-wrap: wrap;
    }

    .onboarded-client-container p {
        text-align: center;
        font-weight: bolder;
        margin-top: 0;
        font-size: 1em;
        color: #2f4d5a;
    }

    .onboarded-client-container h1 {
        font-size: 2.75em;
        text-align: center;
        margin-bottom: 0;
        color: #2f4d5a;
    }

    .call-to-action-section {
        background-color: #2a2c39;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .call-to-action-description-container {
        width: 70%;
        padding: 15px;
    }

    .call-to-action-description-container p, .call-to-action-description-container h2 {
        color: #ffffff;
    }

    .call-to-action-section button {
        background-color: #ee334e;
        color: #ffffff;
        font-weight: bolder;
        font-size: 1.25em;
        padding: 15px;
        border: none;
        border-radius: 50px 50px 50px 50px;
    }

    .our-aim-section {
        background-color: #ffffff;
    }

    .our-aim-container {
        text-align: center;
        padding: 15px
    }

    .our-aim-parent-cards-containers {
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;
    }

    .our-aim-cards-containers {
        display: flex;
        flex: 2;
        background-color: #f7f7f7;
        flex-direction: column;
        align-items: center;
        height: fit-content;
    }

    .our-aim-cards {
        width: 80%;
        height: 40vh;
        justify-content: center;
    }

    .services-image-container {
        flex: 1;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .services-image {
        height: 40vh;
    }

    @media (min-width: 810px) {
        .our-aim-parent-cards-containers {
            flex-direction: row;
        }

        .our-aim-cards-containers {
            flex-direction: row;
            justify-content: space-around;
        }

        .our-aim-cards {
            width: 30%;
        }
    }
</style>