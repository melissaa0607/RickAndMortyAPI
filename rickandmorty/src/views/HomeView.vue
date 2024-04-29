<script setup>
import { onMounted, ref } from 'vue';
import ListRickAndMortys from '../components/ListRickAndMortys.vue';

let rickandmortys = ref([]);

onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character")
  .then(response => response.json())
  .then(data => {
    rickandmortys.value = data.results;
  })
})
</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-6">
          <div class="card" style="width:25rem;">
            <img src="https://upload.wikimedia.org/wikipedia/commons/b/b1/Rick_and_Morty.svg" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">Rick and Morty</h5>
              <p class="card-text">Lista de personagens:</p>
            </div>
          </div>
        </div>
        <div class="col-sm-12 col-md-6">
          <div class="card">
            <div class="card-body row">
              <ListRickAndMortys
                v-for="rickandmorty in rickandmortys"
                :key="rickandmorty.id"
                :name="rickandmorty.name"
                :species="rickandmorty.species"
                :gender="rickandmorty.gender"
                :status="rickandmorty.status"
                :location="rickandmorty.location.name"
                :episodes="rickandmorty.episode.length"
                :url="rickandmorty.image"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
