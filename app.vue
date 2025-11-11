  <template>
    <main class="text-white bg-[#1E1E1E]" >
      <section class="flex flex-col w-full max-w-[1224px] mx-auto gap-8"> 
        <div class="flex flex-wrap gap-4 justify-center">
        <header class="flex gap-4">
          <h2 class="font-bold text-2xl">Personagens</h2>

          <button class="flex gap-2 p-1 pr-2 bg-[#313234] rounded-[32px]"> 
            <IconsSquareFour/>Ver todos
          </button>
        </header>
      
        <div v-for="currentCharacter of data.results" class="bg-[#313234] rounded-lg flex gap-4 flex-col p-4 w-full max-w-[294px]">
          
          
          <img :src="currentCharacter.image" height="200" width="262" class="rounded-lg h-[200px] object-cover"/>
          
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
            <IconsHeartFilled v-if="currentCharacter.status === 'Alive'"/>
            <IconsHeartOutlined v-else/>
          </span>
        </div>
        
        <NuxtLink 
        :to="currentCharacter.url" 
        class="mt-auto self-end bg-[#11B0C8] flex gap-2 py-[6px] pl-1 pr-2 rounded-3xl text-sm items-center"
        target="_blank"
        >
        <IconsInfo />
        Saiba Mais
      </NuxtLink>
      
          
      </div>
    </div>
  </section> 
</main>
</template>

<script lang="ts" setup>
  const { data, status, error, refresh, clear } = await useFetch('https://rickandmortyapi.com/api/character', {
})

console.log(data.value);
</script>