<script setup>
// Use axios for your fetch calls
import { computed, inject, ref } from 'vue'

const axios = inject('axios')

const allSports = ref(undefined)
const sports = ref(undefined)
const teams = ref(undefined)
const events = ref(undefined)
const bets = ref(undefined)

axios.get('all-sports').then(({ data }) => (allSports.value = data))
axios.get('sports').then(({ data }) => (sports.value = data))
axios.get('teams').then(({ data }) => (teams.value = data))
axios.get('events').then(({ data }) => (events.value = data))
axios.get('bets').then(({ data }) => (bets.value = data))

const sportsWithEventsComputed = computed(() => sports.value.map(sport => {
  const theSport = {}
  theSport.name = sport.name
  theSport.events = sport.eventIds.map(id => {
    return events.value.reduce((events, event) => {
      if(event.id === id){
        events.id = id
        events.team1 = teams.value.find(team => team.id === event.participants[0].id)
        events.team1 = events.team1.name
        events.team1bets = event.participants[0].betIds
        events.team2 = event.participants[1].id
        events.team2bets = event.participants[1].betIds
      }

      return events
    }, {})
  })

  return theSport
}, console.log(sportsWithEventsComputed)))
</script>

<template>
  Homepage
</template>
