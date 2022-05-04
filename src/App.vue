<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div> 
      <div class="w3-bar w3-brown">
        <div class="wrapper">
          <RouterLink to="/" class="w3-left brand">
            <img src="@/assets/free-movies-icon-16.png" alt="Logo"> 
            Movies App
          </RouterLink>
          <div class="w3-right">
            <RouterLink to="/" class="w3-button w3-bar-item w3-hover-deep-orange">Home</RouterLink>
            <RouterLink to="/about" class="w3-button w3-bar-item w3-hover-deep-orange">About</RouterLink>
            <RouterLink to="/movies" class="w3-button w3-bar-item w3-hover-deep-orange">Movies</RouterLink>
          </div>
        </div>
      </div>
    </div>
  </header>

  <div class="wrapper">
    <RouterView />
  </div>
</template>

<style>
.wrapper {
  width: 960px;
  margin: 0 auto;
}
.brand {
  text-decoration: none;
  font-weight: 600;
}
.brand > img {
  height: 40px;
  width: 40px;
  padding: 3px;
}
</style>
