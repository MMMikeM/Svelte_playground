<script>
  import Button from '../components/Button.svelte'

  const title = 'This is a title'
</script>

<h1 class="bg-red-500 text-4xl font-black p-4">{title}</h1>
<div class="m-4">
  <a href="/counter">
    <Button>Counter</Button>
  </a>
  <a href="/about">
    <Button>About us</Button>
  </a>
  <a href="/content">
    <Button>Content</Button>
  </a>
</div>
