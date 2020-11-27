<!-- <h3>hi from expense form</h3> -->

<script>
  import Title from './Title.svelte'
  let name = ""
  let amount = null

  // $: console.log({name, amount})

// !! truthy value is TRUE when
// encountered in boolean context
// "" and null are both falsy
/* if (name) {
  console.log(name)
}*/
// return true if both of them are false
$: isEmpty = !name || !amount

function handleSubmit(){
  // do with modifier instead
  // evt.preventDefault()
  console.log({name, amount})
  // nulled (with 2way binding )))
  name=''
  amount = null
}


</script>


{isEmpty}
<!-- <p>name: {name}</p>
<p>amount: {amount}</p> -->
<section class='form'>
  <Title title="add some expense"/>
  <form
    class='expense-form'
    on:submit|preventDefault={handleSubmit}
    >
    <div class='form-control'>
      <!-- need input with the same id -->
      <label for='name'>Name</label>
      <input type='text' id="name" bind:value={name}>
    </div>
    <div class='form-control'>
      <!-- disabled button class example
      class={isActive ? 'active' :''}
      class:active={isActive} svelte way
      class:active={active} if names 'active' are the same
      -->

      <!-- need input with the same id -->
      <label for='amount'>Amount</label>
      <input type='number' id="amount" bind:value={amount}>
    </div>
    {#if isEmpty}
      <p class='form-empty'>fill all form fields</p>
    {/if}
    <button
      type='submit'
      class='btn btn-block'
      class:disabled={isEmpty}
      disabled={isEmpty}
    >
    add expense
    </button>
    <button type="button" class='close-btn'>
      <i class='fas fa-times'></i>
      close
    </button>
  </form>
</section>