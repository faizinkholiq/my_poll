<script>
    export let type = 'primary';
</script>

<button class={type}>
    <slot></slot>
</button>

<style>
    .primary {
        padding: 7px 14px;
        font-weight: 500;
        font-size: 15px;
        color: white;
        background-color: #d91b42;
        border: none;
        border-radius: 45px;
        box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.1);
        cursor: pointer;
        outline: none;
    }

    .primary:focus {
        color: white;
        background-color: #d91b42;
    }
</style>