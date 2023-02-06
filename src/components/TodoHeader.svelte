<script lang="ts">
    import {list} from '../store/todo'
    import Button from "./Button.svelte";
    import Input from "./Input.svelte";

    let title = ''
    const add = () => {
        list.add({title: title, id: new Date().valueOf(), created: new Date()})
    }
</script>

<div class="todo-header">
    <Input bind:value={title} placeholder="title" on:enter={add}/>
    <Button on:click={add}>
        Add
    </Button>
    <Button on:click={() => list.removeAll()}>
        Remove all
    </Button>
</div>

<style>
    .todo-header {
        background: darkred;
        padding: 10px;
        display: flex;
        gap: 10px;
    }
</style>