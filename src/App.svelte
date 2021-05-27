<script>
	import { setContext } from "svelte";
	const state = {
		name: "simple name",
		remove: removeExpense,
		removeAll: removeAllExpenses,
	};
	//components
	import Navbar from "./Navbar.svelte";
	import ExpensesList from "./ExpensesList.svelte";
	//data
	import expensesjs from "./expenses";
	import Expense from "./Expense.svelte";
	let expenses = [...expensesjs];
	//reactive
	$: totalAmount = expenses.reduce((acc,curr)=>{
		return(acc+=curr.amount);
	},0);
	
	//functions
	function removeExpense(id) {
		expenses = expenses.filter((item) => item.id !== id);
	}
	function removeAllExpenses() {
		expenses = [];
	}
	//context
	setContext("state", state);
</script>

<Navbar />
<main class="content">
	<ExpensesList expensesList={expenses} {totalAmount} />
</main>

<style>
</style>
