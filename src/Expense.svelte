<script>
  /* export let expense
  let {name, amount} = expense
  console.log(expense) */

  // since passed desttructured expense object
  export let id
  export let name =''
  export let amount = 0
</script>


<!-- <h4>{index+1} {name} {amount}</h4> -->
<article class="single-expense">
<div class='expense-info'>
  <h3>
    {name}
    <button class='amount-btn'>
      <i class='fas fa-caret-down'></i>
    </button>
  </h3>
  <h3>amount: BYN {amount}</h3>
</div>
<div class='expense-buttons'>
  <button class='expense-btn edit-btn'>
    <i class='fas fa-pen'></i>
  </button>
  <button class='expense-btn delete-btn'>
    <i class='fas fa-trash'></i>
  </button>
</div>
</article>


