<script>
  import Button from '../components/Button.svelte'

  const title = 'This is a title'
  let count = {
    value: 0,
    increment: () => count.value++,
    decrement: () => count.value--
  }
</script>

<h1 class="bg-primary-300 text-4xl font-black p-4">{title}</h1>
<div class="w-1/4 mx-auto flex flex-col">
  <p class="mx-auto font-black text-5xl my-8">{count.value}</p>

  <div class="flex flex-row">
    <Button className="mx-2 flex-grow " onClick={count.increment}>Increment</Button>
    <Button className="mx-2 flex-grow" onClick={count.decrement}>Decrement</Button>
    <a href="/">
      <Button className="mx-2 flex-grow" onClick={count.decrement}>Home</Button>
    </a>
  </div>
</div>
