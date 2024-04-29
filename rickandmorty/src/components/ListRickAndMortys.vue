<script setup>
const props = defineProps(['name', 'species', 'gender', 'status', 'location', 'episodes', 'url']);

const imageUrl = props.url; // Use the direct URL if provided, or construct if needed
console.log(imageUrl);
</script>

<template>
  <div class="container" style="max-width: 300px;">
    <div class="card border-card mb-3">
      <div class="class-header"></div>
      <img :src="imageUrl" height="300" alt="">
      <div class="card-body text-dark">
        <h2 class="card-title">{{ name }}</h2>
        <p class="card-text">Espécie: {{ species }}</p>
        <p class="card-text">Gênero: {{ gender }}</p>
        <p class="card-text">Status: {{ status }}</p>
        <p class="card-text">Localização: {{ location }}</p>
        <p class="card-text">Episódios: {{ episodes }}</p>
      </div>
    </div>
  </div>
</template>

