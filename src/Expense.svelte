<script>
    import ExpensesList from './ExpensesList.svelte';
    export let data;
    export let removeExpense;
    let displayAmount = false;
    function display(){
        displayAmount = !displayAmount;
    }
</script>
<style>
    
</style>
<article class="single-expense">
    <div class="expense-info">
        <h2>{data.name}
        <button on:click={display} class="amount-btn"><i class="fas fa-caret-down"></i></button>
    </h2>
    {#if displayAmount}<h4>amount: ${data.amount}</h4> {/if}
    
    </div>
    <div class="expense-btn">
        <button class="expense-btn edit-btn">
            <i class="fas fa-pen"></i>
        </button>
        <button on:click={()=> removeExpense(data.id)} class="expense-btn delete-btn">
            <i class="fas fa-trash"></i>
        </button>
    </div>

</article>

    

