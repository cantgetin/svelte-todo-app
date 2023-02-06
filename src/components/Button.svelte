<script lang="ts">
    import {createEventDispatcher} from "svelte";
    const dispatch = createEventDispatcher()
    const onClick = (e: any) => {
        dispatch('click', e)
    }
</script>

<button class="button" on:click={onClick}>
    <slot/>
</button>

<style lang="scss">
    .button {
      cursor: pointer;
      background: indianred;
      color: white;
      padding: 10px 20px;
      border: 0;
      border-radius: 5px;
      outline: none;
    }
</style>