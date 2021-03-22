<script>
import { fly } from "svelte/transition";
    let todoItem = '';
    let todoList = [];
    // add items from input field to array
    function addToList() {
        if (!todoItem) return;
        todoList = [...todoList, {
            text: todoItem,
            status: false
        }];
        todoItem = '';
    }
    // remove items from array
    function removeFromList(index) {
        todoList.splice(index, 1);
        todoList = todoList;
    }
</script>

<form on:submit|preventDefault={addToList}>
    <input bind:value={todoItem}>
</form>

<ol class="todo-list">
    {#each todoList as item, index}
    <li transition:fly="{{ y: 20, duration: 200 }}">
    <input bind:checked={item.status} class="checkbox" type="checkbox">
    <span class:checked={item.status}>{item.text}</span>
    <button class="delete" type="button" on:click={() => removeFromList(index)}></button>
    </li>
    {/each}
</ol>


<style>
    .todo-list {
        list-style: none;
    }
   .checked {
       text-decoration: line-through;

   }
   .todo-list {
       color: cornsilk;
       border-style: dashed;
       border-color: #581845;
       width: 300px;
       margin-left: 580px; 
       margin-bottom:500px;  
   }
   input {
       background-color: rgb(110, 68, 110);
       border-color: black;
       color:lawngreen;
   }
   @media (min-width: 640px) {
    .todo-list { 
       width: 300px; 
       margin-bottom:500px;  
   }
	}
</style>