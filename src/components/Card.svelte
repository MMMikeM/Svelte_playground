<script>
  export let pokemon
  export let index
</script>

<div class="shadow-md w-[120px] rounded-lg bg-light-200">
  <img
    src={`https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${
      index + 1
    }.png`}
    alt="img"
    class="mx-auto"
  />
  <h6 class="text-center capitalize">{pokemon.name}</h6>
</div>
