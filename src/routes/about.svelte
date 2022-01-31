<script context="module">
  import Button from '../components/Button.svelte'

  export const load = async ({ fetch }) => {
    const res = await fetch('https://randomuser.me/api/?nat=us&randomapi')
    const data = await res.json().then((res) => res.results[0])

    if (res.ok) {
      return {
        props: {
          data
        }
      }
    } else {
      return {
        status: res.status,
        error: new Error('Request failed!')
      }
    }
  }
</script>

<script>
  const title = 'Basic data fetching'

  export let data
</script>

<h1 class="bg-red-500 text-4xl font-black p-4">{title}</h1>
<div class="m-4 flex flex-col w-[200px]">
  <div>
    Gender: {data.gender}
  </div>
  <div>
    Name: {data.name.first}
    {data.name.last}
  </div>
  <div>
    Location: {data.location.country}
    {data.location.state}
  </div>
  <div>
    E-mail: {data.email}
  </div>
  <div>
    Age: {data.dob.age}
  </div>
  <div>
    Years registered: {data.registered.age}
  </div>
  <div>
    Phone: {data.phone}
  </div>
  <div>
    Cell: {data.cell}
  </div>
  <img src={data.picture.large} alt={`A picture of ${data.name.first}`} />
  <div>
    Nationality: {data.nat}
  </div>

  <a href="/" class="pt-4"><Button>Home</Button></a>
</div>
