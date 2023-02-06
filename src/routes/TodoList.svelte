<script lang="ts">
    import {list} from '../store/todo'
    import TodoAdd from "./TodoAdd.svelte";
</script>

<TodoAdd/>

<div class="item-list">
    {#each $list as item}
        <div class="item-list--item">
            <div>{item.title}</div>
            <div>{item.created}</div>
        </div>
    {/each}
</div>

<style>
    .item-list {
        display: flex;
        flex-wrap: wrap;
        padding: 10px;
        gap: 10px;
    }

    .item-list--item {
        width: 10vw;
        border: 1px solid black;
        height: fit-content;
        background: white;
    }
</style>