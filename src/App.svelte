<script>
  import { setContext } from 'svelte'

  const state = {
    name: "simple name",
    remove: removeExpense
  }

  import Title from './Title.svelte';
  import Navbar from './Navbar.svelte';
  import ExpensesList from './ExpensesList.svelte'

  // load data from outside
  import expencesData from './expenses'

  // load data to app to iterate through
  let expenses = [...expencesData] //make a local copy
  // console.log(expences)

  //
  function removeExpense(id){
    console.log(`remove ${id}`)
    expenses = expenses.filter(i => i.id !== id)
  }

  // context
  // setContext('remove', removeExpense)
  setContext('state', state)

</script>





<Navbar/>
<main class='content'>
  <!-- <ExpensesList expenses={expenses} />
  can be written like this -->
  <ExpensesList {expenses} />
</main>
