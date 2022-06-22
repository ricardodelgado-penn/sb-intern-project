<script setup>
// Use axios for your fetch calls

import HeaderBar from '../components/HeaderBar.vue';
import { onMounted } from 'vue'
import { inject } from 'vue'
import { makeBlock } from '@vue/compiler-core';
const axios = inject('axios')


const allSports = [];
const events = [];
const bets = [];
const teams = [];
const icons = [{key: 'mlb', icon: '@/public/assets/sports_baseball_FILL0_wght400_GRAD0_opsz48.png'}, {key: 'nfl', icon: ''}];



const getAllSports = () => {
axios.get('/all-sports').then(response => {
    allSports.value = response.data
    });

    for( let i = 0; i < allSports.length; i++ ){
        let thisKey = allSports[i].key
        for(let i = 0; i < icons.length; i++){
        if(thisKey == icons[i].key){
        allSports[i]['icon'] = icons[i].icon
        }
    }
    }

    console.log('allSports', allSports)
}

const getEvents = () => {
axios.get('/events').then(response => {
    events.value = response.data
    });

    console.log('events', events)
}

const getBets = () => {
axios.get('/bets').then(response => {
    bets.value = response.data
    });

    console.log('bets', bets)
}

const getTeams = () => {
axios.get('/teams').then(response => {
    teams.value = response.data
    });

    console.log('teams', teams)
}

onMounted(() => getAllSports(), getEvents(), getBets(), getTeams())



</script>

<template>
<HeaderBar :allSports="allSports" :key="allSports.key" :name="allSports.name" />
</template>

<style scoped>

</style>
