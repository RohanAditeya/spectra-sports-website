<script setup lang="ts">
  import { Icon } from '@iconify/vue'
  import logoUrl from '../static/spectra-logo.svg'
</script>

<template>
  <header>
    <div :class="['navbar']">
      <img :class="['logo-img']" :src="logoUrl" alt="Spectra Sports Logo"/>
      <div :class="['menu']">
        <Icon icon="radix-icons:hamburger-menu" :class="['menu-icon']"/>
      </div>
    </div>
  </header>
</template>

<style lang="css" scoped>
  header {
    max-height: var(--header-height);
    border-bottom-color: #ee334e;
    border-bottom-width: thin;
    border-bottom-style: solid;
  }
  .navbar {
    display: flex;
    height: var(--header-height);
    justify-content: space-between;
  }
  .logo-img {
    max-height: 110%;
    flex: 1;
  }
  .menu {
    display: flex;
    justify-content: flex-end;
    padding: 15px;
    align-items: center;
    flex: 1;
  }
  .menu-icon {
    font-size: 2em;
  }
</style>