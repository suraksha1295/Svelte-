<script>
  import { getContext,createEventDispatcher } from "svelte";

  
  export let id;
  export let name = "";
  export let amount = 0; 
 
  
  
  let displayAmount = false;
  
  
  function toggleAmount() {
    displayAmount = !displayAmount;
  }

  const removeExpense = getContext('remove');

  const distpatch = createEventDispatcher; 
</script>

<article class="single-expense">

  <div class="expense-info">
    <h2>
      {name}
      <button class="amount-btn" on:click={toggleAmount}>
        <i class="fas fa-caret-down" />
      </button>
    </h2>

    {#if displayAmount}
      <h4>amount : ${amount}</h4>
    {/if}

  </div>

  <div class="expense-button">
    <button class="expense-btn edit-btn" >
      <i class="fas fa-pen" />
    </button>

    <button class="Expense-btn delete-btn" on:click= {removeExpense(id)}>
    <i class = "fas fa-trash" />
  </div>
</article>
