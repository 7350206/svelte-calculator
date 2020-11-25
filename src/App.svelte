<script>
	import Title from './Title.svelte';
	import Navbar from './Navbar.svelte';

  let fruits = ["apple", "orange", "banana"]

</script>


<Navbar/>

<!-- #each block allows to render a list -->
{#each fruits as item}
  <h3>fruit: {item}</h3>
  <Title title={item}/>
{/each}
