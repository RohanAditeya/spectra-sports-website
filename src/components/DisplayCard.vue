<script setup lang="ts">
    import { Icon } from '@iconify/vue'
    import type { DisplayCardProps } from '@/types/InterfaceTypes';

    const {isPositionRelative = false, isWidthFractional = false} = defineProps<DisplayCardProps>()
</script>

<template>
    <article :class="['service-card', isPositionRelative ?  'service-card-relative' : '', isWidthFractional ? 'service-card-fraction-width' : '']">
        <div :class="['service-card-icon-container']">
            <Icon :icon="iconName" width="45" height="45" />
        </div>
        <h2 :class="['service-card-heading']">{{ cardHeader }}</h2>
        <p :class="['service-card-description']">
            {{ cardDescription }}
        </p>
    </article>
</template>

<style lang="css" scoped>

    .service-card {
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-around;
        background-color: #ffffff;
        padding: 15px;
	    box-shadow: 0px 2px 15px rgba(0, 0, 0, 0.1);
        margin: 10px 0;
    }

    .service-card-fraction-width {
        width: 80%;
    }

    .service-card-relative {
        position: relative;
        top: -80px;
    }

    .service-card-heading {
        color: #2f4d5a;
    }

    .service-card-description {
        text-align: center;
    }

    @media (min-width: 810px) {
        .service-card-fraction-width {
            max-width: 30%;
        }
    }

    @media (min-width: 1025px) {
        .service-card-fraction-width {
            max-width: 20%;
        }        
    }
</style>