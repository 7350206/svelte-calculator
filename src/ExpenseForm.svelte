<!-- <h3>hi from expense form</h3> -->

<script>
  import Title from './Title.svelte'
  let name = ""
  let amount = null

  // $: console.log({name, amount})
</script>

<!-- <p>name: {name}</p>
<p>amount: {amount}</p> -->
<section class='form'>
  <Title title="add some expense"/>
  <form class='expense-form'>
    <div class='form-control'>
      <!-- need input with the same id -->
      <label for='name'>Name</label>
      <input type='text' id="name" bind:value={name}>
    </div>
    <div class='form-control'>
      <!-- need input with the same id -->
      <label for='amount'>Amount</label>
      <input type='number' id="amount" bind:value={amount}>
    </div>
    <p class='form-empty'>fill all form fields</p>
    <button type='submit' class='btn btn-block'>
      add expense
    </button>
    <button type="button" class='close-btn'>
      <i class='fas fa-times'></i>
      close
    </button>
  </form>
</section>