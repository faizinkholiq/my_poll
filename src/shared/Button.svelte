<script>
    export let type = 'primary';
    export let flat = false;
</script>

<button class={type} class:flat={flat}>
    <slot></slot>
</button>

<style>
    button {
        padding: 7px 14px;
        font-weight: 500;
        font-size: 15px;
        border: none;
        border-radius: 45px;
        box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.1);
        cursor: pointer;
        outline: none;
    }

    .primary{
        color: white;
        background: #d91b42;
    }

    .primary:focus {
        color: white;
        background: #d91b42;
    }

    .secondary{
        color: white;
        background: #45c496;
    }

    .secondary:focus {
        color: white;
        background: #45c496;
    }

    .flat{
        box-shadow: none;
    }
</style>