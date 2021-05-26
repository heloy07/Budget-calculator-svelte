<script>
	import {setContext} from 'svelte';
	const state = {
		name:'simple name',
		remove:removeExpense
	}
	//components
	import Navbar from './Navbar.svelte';
	import ExpensesList from './ExpensesList.svelte';
	//data
	import expensesjs from './expenses';
	let expenses = [...expensesjs];
	//functions
	function removeExpense(id){
		expenses = expenses.filter(item => item.id !== id);
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