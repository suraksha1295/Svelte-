<script>
import Navbar from './Navbar.svelte';
import Title from './Title.svelte';
import expensesData from './expenses';
import ExpenseList from './ExpenseList.svelte';

import {setContext} from 'svelte';

//functions 
function removeExpense(id){
	expenses = expenses.filter(item => item.id !== id);
}
//context 
setContext('remove', removeExpense)

let expenses = [...expensesData];


</script>

<style></style>


<Navbar />

<main class="content">
<ExpenseList {expenses} {removeExpense}/>
</main>


