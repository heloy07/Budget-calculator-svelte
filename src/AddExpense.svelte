<script>
    import Title from "./Title.svelte";
    import { getContext } from "svelte";
    import { is_empty } from "svelte/internal";
    let name = "";
    let amount = null;
    //without the inline syntax I get an error from -- 'property call of undefined from index.mjs'
    const { addExpense } = getContext("state");
    //truthy value is considered TRUE when encountered in boolean context, so if they're empty or null it will be evaluated to false
    $: isEmpty = !name || !amount;

    function handleSubmit(){
        addExpense(name,amount);
        //reset form
        name='';
        amount=null;
    }
</script>

<section class="form">
    <Title title="Add expense" />
    <form
        on:submit|preventDefault={handleSubmit}
        class="expense-form"
    >
        <div class="form-control">
            <label for="name">name</label>
            <input type="text" id="name" bind:value={name} />
        </div>
        <div class="form-control">
            <label for="amount">amount</label>
            <input type="number" id="amount" bind:value={amount} />
        </div>
        {#if isEmpty}
            <p class="form-empty">please fill out all from fields</p>
        {/if}

        <button type="button" class="close-btn"
            ><i class="fas fa-times" />close</button
        >
        <button type="submit" 
                disabled={isEmpty} 
                class="btn btn-block "
                class:disabled={isEmpty}>
                add expense</button>
    </form>
</section>
