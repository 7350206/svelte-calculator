<script>
  import SectionTitle from './Title.svelte'
  import Expense from './Expense.svelte'

  // !! tell parent - prop can be passed into component
  export let expenses = [] // !! prop itself
  export let removeExpense


  console.log(expenses)
</script>



<!--

  {#each expression as item} ... {:else}... {/each}
  else - if the case no items in list yet|already
-->

<style>
  h3{
    text-transform: capitalize;
  }
</style>

<section>
  <SectionTitle title="expense list" />
  <ul>
    {#each expenses as expense, index}
      <!-- <Expense index={index+1} /> -->
      <!-- <Expense {index}{expense}  />  -->
      <Expense {...expense} {removeExpense} />
      {:else}
      <h3>theres no expenses to display</h3>
    {/each}
  </ul>
</section>