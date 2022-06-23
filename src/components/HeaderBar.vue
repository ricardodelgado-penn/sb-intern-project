<script setup>
import IconBaseball from '../components/icons/IconBaseball.vue';
import IconBasketball from '../components/icons/IconBasketball.vue';
import IconFootball from '../components/icons/IconFootball.vue';
import IconHockey from '../components/icons/IconHockey.vue';
import { ref } from 'vue';

const props = defineProps({ allSports: { type: Array, required: true } })
// let thisComponent = ref(IconBaseball)
// ^^^tried to using this to make the component :is dynamic, but will circle back to it
</script>


<template>
  <div class="container">
    <div class="sports-wrapper">
      <div 
      class="sport" 
      v-for="sport in allSports" :key="sport.key"
      >

      <component class="icon" v-if="sport.key === 'mlb'" 
      :is="IconBaseball"></component>
      
      <component class="icon" v-else-if="sport.key === 'nhl'" 
      :is="IconHockey" ></component>
      
      <component class="icon" v-else-if="sport.key === 'nba'" 
      :is="IconBasketball"></component>
      
      <component class="icon" v-else-if="sport.key === 'nfl'" 
      :is="IconFootball"></component>
      
      {{ sport.key.toUpperCase() }}
      </div>
    </div>
  </div>
</template>

<style>
.container {
  width: 100%;
}

.sports-wrapper {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}

.sport {
  display: flex;
  justify-content: center;
  align-items: center;
}

.icon {
  margin-right: 10px;
}
</style>