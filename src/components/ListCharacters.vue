<script setup>
const character = defineProps(["name", "url", "status", "species", "gender", "location", "episode"])
const characterId = character.url.split('/')[5]
const imageUrl = "https://rickandmortyapi.com/api/character/avatar/" + characterId + ".jpeg"
const nextPage = () => {
    if (page.value) {
        fetch(page.value)
    }
}

</script>

<template>
    <div class="col-md-4">
        <div class="card p-2 mb-3">
            <img :src="imageUrl" alt="">
            <p class="text-center"><b>Name:</b> {{ character.name }}</p>
            <p class="text-center"><b>Status:</b> {{ character.status }}</p>
            <p class="text-center"><b>Specie:</b> {{ character.species }}</p>
            <p class="text-center"><b>Gender:</b> {{ character.gender }}</p>
            <p class="text-center"><b>Current location:</b> {{ character.location.name }}</p>
            <p class="text-center"><b>Episodes: </b> {{ character.episode.length }}</p>
        </div>
    </div>
</template>

<style>
</style>