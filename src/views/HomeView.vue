<script setup>
  import {onMounted, reactive, ref} from 'vue';
  import ListCharacters from '../components/ListCharacters.vue';

  const page = ref(null);
  let characters = reactive(ref());

  onMounted(() => {
    fetch("https://rickandmortyapi.com/api/character")
    .then(response => response.json())
    .then(response => {
      characters.value = response.results
      page.value = response.info.next
      console.log(characters)
      console.log(page)
    })
  })
</script>



<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-12">
          <div class="card">
            <div class="card-body row">
              <ListCharacters v-for="character in characters"
              :key="character.name" 
              :name="character.name"
              :url="character.url"
              :status="character.status"
              :species="character.species"
              :gender="character.gender"
              :location="character.location"
              :episode="character.episode"
              />
            </div>
          </div>
        </div>
      </div>
      <!-- Tentativa de criar botão que carrega a próxima página da API
      <center>
        <ListCharacters>
          <button @click="nextPage()">Carregar mais</button>
        </ListCharacters>
      </center> -->
    </div>
  </main>
</template>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Jersey+20+Charted&display=swap');

/* button{
  padding: 10px;
  margin: 10px;
  border-radius: 7px;
  background-color: #35c9dd;
} */

</style>