<script>
	import {setContext} from 'svelte';
	const state = {
		name:'simple name',
		remove:removeExpense,
		removeAll:removeAllExpenses
	}
	//components
	import Navbar from './Navbar.svelte';
	import ExpensesList from './ExpensesList.svelte';
	//data
	import expensesjs from './expenses';
import Expense from './Expense.svelte';
	let expenses = [...expensesjs];
	//functions
	function removeExpense(id){
		expenses = expenses.filter(item => item.id !== id);
	}
	function removeAllExpenses(){
		expenses = [];
	}
	//context
	setContext('state',state);
</script>
<Navbar/>
<main class="content">
	
	<ExpensesList expensesList={expenses} />

	
	
</main>

<style>

</style>