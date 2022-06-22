<script setup>
const props = defineProps({ allSports: {type: Array, required: true} })



</script>

<template>
  <div class="container">
    <div class="sports-wrapper">
      <p v-for="sport in props.allSports.value" :key="sport.key"> {{ sport.name }} | {{sport.key.toUpperCase()}} </p>
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
}
</style>