<script>
    import Title from "./Title.svelte";
    import {getContext} from 'svelte';
    let name ='';
    let amount = null;
    const {addExpense}  = getContext('state');
    //without the inline syntax I get an error from -- 'property call of undefined from index.mjs'
   
</script>

<section class="form">
    <Title title="Add expense" />
    
    <form on:submit|preventDefault={()=>addExpense(name,amount) } class="expense-form">
        <div class="form-control">
            <label for="name">name</label>
            <input type="text" id="name" bind:value={name}/>
        </div>
        <div class="form-control">
            <label for="amount">amount</label>
            <input type="number" id="amount" bind:value={amount}/>
        </div>
        <p class="form-empty">please fill out all from fields</p>

        
        <button type="button" class="close-btn"><i class="fas fa-times"></i>close</button>
        <button type="submit" class="btn btn-block ">add expense</button>
    </form>
</section>
