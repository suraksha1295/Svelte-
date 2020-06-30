<script>
import SectionTitle from './Title.svelte';
import SingleExpense from './SingleExpense.svelte';

export let expenses = [];
</script>

<section>
<SectionTitle title="expense list" />
</section>

<ul>
{#each expenses as expense, index (expense.id)}
     <SingleExpense {expense} />
{:else}
<h2>No expenses</h2>
    {/each}
</ul>


<style>
h2{
    text-transform: capitalize;
}
</style>