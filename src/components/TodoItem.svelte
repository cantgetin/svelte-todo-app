<script lang="ts">
    import {createEventDispatcher} from "svelte";
    import dayjs from 'dayjs';
    import type ITodo from "../interfaces/ITodo";

    const dispatch = createEventDispatcher()

    const onClick = () => {
        dispatch('remove')
    }
    export let item: ITodo;
</script>

<div class="list-item">
    <div class="list-item--title">{item.title}</div>
    <div class="list-item--createdAt">{dayjs(item.created).format('DD.MM.YYYY HH.mm:ss')}</div>
    <div class="list-item--remove" on:click={onClick}>X</div>
</div>

<style>
    .list-item {
        min-width: 100px;
        width: 10vw;
        padding: 10px;
        border-radius: 5px;
        background: indianred;
        color: white;
        height: 7vh;
        position: relative;
    }
    .list-item--title {
        font-size: 25px;
    }
    .list-item--createdAt {
        color: lightgrey;
    }
    .list-item--remove {
        background: darkred;
        height: 25px;
        width: 25px;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 5px;
        cursor: pointer;
        position: absolute;
        top: 5px;
        right: 5px;
    }
</style>