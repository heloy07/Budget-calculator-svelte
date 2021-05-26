<script>
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
	
</script>
<Navbar/>
<main class="content">
	
	<ExpensesList expensesList={expenses} {removeExpense}/>

	
	
</main>

<style>

</style>