<script context="module">
  export async function load({ fetch }) {
    const res = await fetch('https://pointercrate.com//api/v2/demons/listed/?limit=10');
    const data = await res.json();
    if (res.ok) {
      return {
	props: { demon: data }
      }
    }
  }
</script>

<script>
  import Demons from '../components/Demons.svelte';
  export let demon;
</script>

<body>
  <section>
    <h1>GD Demon List</h1>
    <p>Made by <a href="https://github.com/Fizzify" target="__blank">Fizzify</a></p>
    <p>Made possible by <a href="https://github.com/stadust/pointercrate" target="__blank">Pointercrate's API</a>.</p>
    <Demons {demon} />
    <footer>Here is the <a href="https://github.com/Fizzify/gd-demon-list">Github</a>.</footer>
  </section>
</body>
<style>
  body {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    font-family: Arial, "Helvetica Neue", sans-serif;
  }
</style>

<svelte:head>
  <title>GD Demon List</title>
</svelte:head>
