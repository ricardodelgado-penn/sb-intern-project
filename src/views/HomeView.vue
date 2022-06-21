<script setup>
// Use axios for your fetch calls

import HeaderBar from '../components/HeaderBar.vue';
import { onMounted } from 'vue'
import { inject } from 'vue'
const axios = inject('axios')


const allSports = [];
const events = [];
const bets = [];


const getAllSports = () => {
axios.get('/all-sports').then(response => {
    allSports.value = response.data
    });

    console.log(allSports)
}

const getEvents = () => {
axios.get('/events').then(response => {
    events.value = response.data
    });

    console.log(events)
}

const getBets = () => {
axios.get('/bets').then(response => {
    bets.value = response.data
    });

    console.log(bets)
}

onMounted(() => getAllSports(), getEvents(), getBets())


</script>

<template>
  Homepage
    <HeaderBar />
</template>

<style scoped>

</style>
