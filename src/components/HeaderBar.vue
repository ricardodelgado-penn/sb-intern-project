<script setup>
import HomeView from '@/views/HomeView.vue';

</script>

<template>
  <div class="container">
    <div class="sports-wrapper">
        <p v-for="sport in HomeView.allSports" v-bind:key="sport.key" >{{sport.name}}</p>
        <p>test</p>
    </div>
  </div>
</template>

<style>

</style>