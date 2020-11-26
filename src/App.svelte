<script>
	import Title from './Title.svelte';
  import Navbar from './Navbar.svelte';
  import ExpensesList from './ExpensesList.svelte'

  // load data from outside
  import expencesData from './expenses'

  // load data to app to iterate through
  let expenses = [...expencesData] //make a local copy
  // console.log(expences)


  // prop drill pattern
  // function to pass as a prop into Expense component
  function removeExpense(id){
    console.log(`delete ${id}`)
    expenses = expenses.filter(i => i.id !== id)
  }

</script>





<Navbar/>
<main class='content'>
  <!-- <ExpensesList expenses={expenses} />
  can be written like this -->
  <ExpensesList {expenses} {removeExpense} />
</main>
