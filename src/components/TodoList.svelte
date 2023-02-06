<script lang="ts">
    import {list} from '../store/todo'
    import TodoAdd from "./TodoHeader.svelte";
    import TodoItem from "./TodoItem.svelte";
</script>

<TodoAdd/>

<div class="item-list">
    {#each $list as item}
        <TodoItem item={item} on:remove={() => list.remove(item.id)}/>
    {/each}
</div>

<style>
    .item-list {
        display: flex;
        flex-wrap: wrap;
        padding: 10px;
        gap: 10px;
    }
</style>