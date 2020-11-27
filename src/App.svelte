<script>
  import { setContext } from 'svelte'

  const state = {
    name: "simple name",
    remove: removeExpense
  }

  import Totals from './Totals.svelte';
  import ExpenseForm  from "./ExpenseForm.svelte";
  import Title from './Title.svelte';
  import Navbar from './Navbar.svelte';
  import ExpensesList from './ExpensesList.svelte'

  // load data from outside
  import expencesData from './expenses'

  // load data to app to iterate through
  let expenses = [...expencesData] //make a local copy
  // console.log(expences)


  // reactive
  $: totals = expenses.reduce((acc, expense) => {
    console.log({acc, expense:expense.amount})
    return (acc += expense.amount)
  }, 0)


  function addExpense ({name, amount}){
    // console.log(name, amount)
    let expense = {
      id: Math.random()*Date.now(),
      name,
      amount
    }
    // add new exp to infront of existing arr
    expenses = [expense, ...expenses]
  }



  //
  function removeExpense(id){
    console.log(`remove ${id}`)
    expenses = expenses.filter(i => i.id !== id)
  }

  const clearExpenses = () => {
    console.log('clear pushed')
    expenses = []
  }



  // context
  // setContext('remove', removeExpense)
  setContext('state', state)

</script>





<Navbar/>
<main class='content'>
  <!-- <ExpensesList expenses={expenses} />
  can be written like this -->
  <ExpenseForm {addExpense} />
  <Totals title="total amount" {totals}/>
  <ExpensesList {expenses} />

  <button
    type="button"
    class="btn btn-primary btn-block"
    on:click={clearExpenses}
    >clear expenses</button>
</main>
