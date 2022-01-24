<script>
  import Button from '../components/Button.svelte'
  import Card from '../components/Card.svelte'
  import { useQuery, useQueryClient } from '@sveltestack/svelte-query'

  const queryClient = useQueryClient()

  const getPokemons = async () => {
    return await fetch('https://pokeapi.co/api/v2/pokemon?offset=0&limit=151').then((res) =>
      res.json().then((res) => res.results)
    )
  }

  // Queries
  const queryResult = useQuery('pokemons', getPokemons)
</script>

<div>
  <a href="/" class="pt-4"><Button>Home</Button></a>
  <div class="flex flex-row flex-wrap gap-4 w-1/4 mx-auto">
    {#if $queryResult.isLoading}
      <div>Loading...</div>
    {:else if $queryResult.isError}
      <div>Error: {$queryResult.error.message}</div>
    {:else if $queryResult.data}
      {#each $queryResult.data as pokemon, index}
        <Card {pokemon} {index} />
      {/each}
    {/if}
  </div>
</div>
