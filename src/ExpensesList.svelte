<script>
    import Expense from "./Expense.svelte";
    import {getContext} from 'svelte';
    import Title from "./Title.svelte";
    export let expensesList = [];
    const {removeAll} = getContext('state');

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
<button type="button" class="btn btn-primary btn-block" on:click={removeAll}>clear expenses</button>
