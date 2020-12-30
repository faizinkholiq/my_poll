<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    export let tabsItems;
</script>

<div class="tabs">
    <ul>
        {#each tabsItems as item}
            <li on:click={() => dispatch('tabChange', item.name)}>
                <div class:active={item.active}>{item.name}</div>
            </li>
        {/each}
    </ul>
</div>

<style>
    .tabs {
        margin-bottom: 40px;
    }

    .tabs ul {
        display: flex;
        justify-content: center;
        padding: 0;
        list-style-type: none;
    }

    .tabs ul li{
        margin: 0 16px;
        font-size: 18px;
        color: #555;
        cursor: pointer;
    }

    .active {
        color: #d91b42;
        border-bottom: 2px solid #d91b42;
        padding-bottom: 5px;
    }
</style>