<script>
    import Expense from "./Expense.svelte";
    import Title from "./Title.svelte";
    export let expensesList = [];
    export let removeExpense;
</script>
<style>h2{
    text-transform:capitalize;
}</style>

<section>
    <Title title="Expensive List" />
    <ul />
</section>
{#each expensesList as exp}
    <Expense data={exp} {removeExpense} />
    {:else}
    <h2>Currently no expenses</h2>
{/each}
