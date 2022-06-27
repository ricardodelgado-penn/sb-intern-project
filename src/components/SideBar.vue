<script setup>
import LogoBlock from '../components/icons/LogoBlock.vue';
let pages = ['Home', 'Sports', 'Events', 'Teams', 'Preferences' ]
</script>

<template>
  <div class="container">
    <div class="logo-block">
      <LogoBlock />
    </div>
    <div class="pages-wrapper">
      <div
        v-for="page in pages"
        :key="page.id"
        class="page"
      >
        <p>{{ page }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
    display: flex;
    flex-direction: column;
}

.pages-wrapper {
    color: white;
    justify-content: center;
}
</style>
