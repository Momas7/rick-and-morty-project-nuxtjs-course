<template>
  <div class="text-white">
    <h1 class="text-blue-600">trojana</h1>

    <div class="flex flex-wrap w-full max-w-[1224px] gap-4 mx-auto gap-4">
      <div v-for="currentCharacter of data.results" class="bg-[#313234] rounded-lg flex gap-4 flex-col p-4">

        
        <img :src="currentCharacter.image" height="200" width="262" class="rounded-lg"/>

      <div class="grid grid-cols-[1fr,48px]">
        <div class="flex flex-col gap-4">
          
          <p class="text-base font-bold">{{ currentCharacter.name }}</p>

          <div class="flex flex-col gap-2">
            
            <p>
              {{ currentCharacter.status === "Alive" ? "Vivo" : "Morto"}}
            </p>
            <p>{{ currentCharacter.species }}</p>
            <p>{{ currentCharacter.origin.name }}</p>
          </div>
        </div>

        <span>
          <iconsHeartFilled />
        </span>
        </div>

        <NuxtLink :to="currentCharacter.url" class="mt-2">Saiba Mais</NuxtLink>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
  const { data, status, error, refresh, clear } = await useFetch('https://rickandmortyapi.com/api/character', {
})

console.log(data.value);
</script>