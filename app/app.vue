<template>
  <div>
    <h1 class="text-blue-600">trojana</h1>

    <div class="flex w-full max-w-[1224px] gap-4 mx-auto">
      <div v-for="currentCharacter of data">
        <p>{{ currentCharacter }}</p>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
  const { data, status, error, refresh, clear } = await useFetch('https://rickandmortyapi.com/api/character', {
})

console.log(data.value);
</script>