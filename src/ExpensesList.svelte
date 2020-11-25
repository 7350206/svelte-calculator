<script>
  import SectionTitle from './Title.svelte'
  import Expense from './Expense.svelte'
  // prop name that can be passed into
  export let expenses = []
  console.log(expenses)
</script>


<section>
  <SectionTitle title="expense list" />
  <ul>
    {#each expenses as item}
      <Expense />
    {/each}
  </ul>
</section>