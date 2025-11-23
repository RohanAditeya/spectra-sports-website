<script setup lang="ts">
  import { Icon } from '@iconify/vue'
  import logoUrl from '../static/spectra-logo.svg'
</script>

<template>
  <header>
    <div :class="['navbar']">
      <img :class="['logo-img']" :src="logoUrl" alt="Spectra Sports Logo"/>
      <div :class="['menu']">
        <button><Icon icon="radix-icons:hamburger-menu" :class="['menu-icon']"/></button>
        <div :class="['menu-items']">
          <ul>
            <li><p :class="['menu-item']"><strong>Home</strong></p></li>
            <li><p :class="['menu-item']"><strong>Services</strong></p></li>
            <li><p :class="['menu-item']"><strong>Events</strong></p></li>
            <li><p :class="['menu-item']"><strong>Fundraisers</strong></p></li>
            <li><p :class="['menu-item']"><strong>Register</strong></p></li>
            <li><p :class="['menu-item']"><strong>Login</strong></p></li>
          </ul>
        </div>
      </div>
    </div>
  </header>
</template>

<style lang="css" scoped>
  header {
    max-height: var(--header-height);
    border-bottom-color: var(--spectra-red);
    border-bottom-width: thin;
    border-bottom-style: solid;
  }

  .navbar {
    display: flex;
    height: var(--header-height);
    justify-content: space-between;
    align-items: center;
  }

  .logo-img {
    height: 60%;
    width: auto;
    flex: 1;
  }

  .menu {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    flex: 1;
    position: relative;
    height: 100%;
  }

  .menu-icon {
    font-size: 3em;
  }

  .menu-items {
    display: none;
    position: absolute;
    top: 90%;
    right: 0;
    background-color: var(--background-light);
    box-shadow: -5px 5px 18px -6px #000000;
    width: 80%;
  }

  .menu-items ul {
    padding-inline-start: 0px;
  }

  .menu-items li {
    list-style-type: none;
    text-align: right;
    padding: 2px;
    padding-right: 20px;
  }

  .menu button {
    padding: 0;
    margin: 0;
    height: 100%;
    width: auto;
    background-color: var(--background-light);
    border: none;
    padding-right: 15px
  }

  .menu:focus-within .menu-items {
    display: block;
  }

  .menu-item {
    font-family: sans-serif;
  }

  @media (min-width: 810px) {

    .menu {
      flex: 2;
      padding: 0px;
      height: 100%;
    }

    .menu button {
      display: none;
    }

    .menu-items {
      display: block;
      position: static;
      width: 100%;
      box-shadow: none;
      background-color: transparent;
      height: 100%;
      display: flex;
      align-items: center;
    }

    .menu-items ul {
      margin: 0;
      display: flex;
      width: 100%;
      height: 100%;
      justify-content: space-between;
      align-items: center;
    }

    .menu-items li {
      display: flex;
      padding: 0;
      width: 100%;
      height: 100%;
      text-align: justify;
      align-items: center;
      justify-content: center;
    }
  }

  @media (min-width: 1025px) {

    .menu-items li:hover {
      background-color: var(--spectra-red);
      cursor: pointer;
    }

    .menu-items li:hover .menu-item {
      color: white;
    }
  }
</style>