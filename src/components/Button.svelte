<script>
  export let onClick
  export let className
</script>

<button on:click={onClick} class={`btn-primary ${className}`}><slot /></button>
