<script>
	import Title from './Title.svelte';
	import Navbar from './Navbar.svelte';
  import Example from './Example.svelte';
</script>

<style>
  /* works locally  <span>hi from app</span>*/
  /* span {
    background: blue;
    color: white;
  } */
</style>



<Navbar/>
<Title title="Add expence"/>
<Title title="Expence list"/>
<Title />

<Example/>
<span>hi from app</span>
