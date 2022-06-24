<script setup>
import HeaderBar from '../components/HeaderBar.vue';
import { onMounted, inject, ref } from 'vue'
const axios = inject('axios')

const allSports = ref([]);
const events = [];
const bets = [];
const teams = [];

const getAllSports = () => {
    axios.get('/all-sports')
        .then(response => {
            allSports.value = response.data
            console.log('allSports', allSports)
        })
}

const getEvents = () => {
    axios.get('/events')
        .then(response => {
            events.value = response.data
            console.log('events', events)
        })
}

const getBets = () => {
    axios.get('/bets')
        .then(response => {
            bets.value = response.data
            console.log('bets', bets)
        })
}

const getTeams = () => {
    axios.get('/teams')
        .then(response => {
            teams.value = response.data
            console.log('teams', teams)
        })
}

onMounted(() => {
    getAllSports() 
    getEvents()
    getBets()
    getTeams()
});
</script>

<template>
  <HeaderBar
    :key="allSports.key"
    :all-sports="allSports"
    :name="allSports.name"
  />
</template>

<style scoped>

</style>
