<script>
	import Title from './Title.svelte';
  import Navbar from './Navbar.svelte';
  import ExpensesList from './ExpensesList.svelte'


  import expencesData from './expenses'
  let expenses = [...expencesData] //make a local copy
  // console.log(expences)

</script>

<style>
</style>

<Navbar/>
<main class='content'>
  <!-- <ExpensesList expenses={expenses} /> -->
  <ExpensesList {expenses} />
</main>
