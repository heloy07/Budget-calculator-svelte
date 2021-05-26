<script>
	//components
	import Navbar from './Navbar.svelte';
	import ExpensesList from './ExpensesList.svelte';
	//data
	import expensesjs from './expenses';
	let expenses = [...expensesjs];
	
</script>
<Navbar/>
<main class="content">
	
	<ExpensesList expensesList={expenses}/>

	
	
</main>

<style>

</style>