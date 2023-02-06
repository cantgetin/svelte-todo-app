<script lang="ts">
    import {list} from '../store/todo'

    let title = ''
    const add = () => {
        list.add({title: title, id: new Date().valueOf(), created: new Date()})
    }
</script>

<div class="todo-add">
    <input class="add-input" bind:value={title} placeholder="title">
    <button class="add-btn" on:click={add}>
        Add Item
    </button>
</div>

<style>
    .todo-add {
        background: darkred;
        padding: 10px;
    }
    .add-btn {
        padding: 5px 10px;
    }
    .add-input {
        padding: 5px 10px;
    }
</style>