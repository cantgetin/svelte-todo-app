<script lang="ts">
    import {createEventDispatcher} from "svelte";

    export let value = '';
    export let placeholder = '';
    const onInput = (event: any) => {
        value = event.target.value
    }

    const dispatch = createEventDispatcher()
    const onKeydown = (event: KeyboardEvent) => {
        if (event.code === 'Enter') {
            dispatch('enter')
        }
    };
</script>

<input
        class="input"
        on:input={onInput}
        on:keydown={onKeydown}
        {value}
        {placeholder}
>

<style>
    .input {
        padding: 10px 20px;
        border-radius: 5px;
        outline: none;
        border: none;
    }
</style>