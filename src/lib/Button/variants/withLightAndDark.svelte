<script lang="ts">
    export let mode: "light" | "dark" = "light";
</script>

<button
    class="button heading--s-variant {variant === 'dark' ? 'dark' : 'light'}"
>
    <slot />
</button>

<style>
    button {
        border: none;
        border-radius: 24px;
        padding: 16px 24px;
        background-color: var(--color-1);
        cursor: pointer;
        color: #fff;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    button.light {
        background-color: var(--color-11);
        color: var(--color-7);
    }

    button.light:hover {
        background-color: var(--color-5);
    }

    button.dark {
        color: var(--color-5);
        background-color: var(--color-4);
    }

    button.dark:hover {
        background-color: #fff;
    }
</style>
