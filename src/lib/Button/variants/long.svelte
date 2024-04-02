<script lang="ts">
</script>

<button>
    <slot />
</button>

<style>
    button {
        border: none;
        border-radius: 24px;
        padding: 16px 24px;
        background-color: var(--color-11);
        cursor: pointer;
        color: var(--color-7);
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        max-width: 350px;
    }

    button:hover {
        background-color: var(--color-5);
    }
</style>
