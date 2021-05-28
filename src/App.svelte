<script>
	import { setContext } from "svelte";
	const state = {
		name: "simple name",
		remove: removeExpense,
		removeAll: removeAllExpenses,
		addExpense: addExpense
	};
	//components
	import Navbar from "./Navbar.svelte";
	import ExpensesList from "./ExpensesList.svelte";
	import AddExpense from './AddExpense.svelte'
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
	function addExpense(name,amount){
		const expense = {
			id:Math.random() * Date.now(),
			name:name,
			amount:amount
		}
		expenses=[expense,...expenses];
	}
	//context
	setContext("state", state);
</script>

<Navbar />
<main class="content">
	<AddExpense/>
	<ExpensesList expensesList={expenses} {totalAmount} />
</main>

<style>
</style>
