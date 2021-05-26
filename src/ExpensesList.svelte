<script>
    import Expense from "./Expense.svelte";
    import Title from "./Title.svelte";
    export let expensesList = [];

</script>
<style>h2{
    text-transform:capitalize;
}</style>

<section>
    <Title title="Expensive List" />
    <ul />
</section>
{#each expensesList as exp}
    <Expense data={exp} />
    {:else}
    <h2>Currently no expenses</h2>
{/each}
