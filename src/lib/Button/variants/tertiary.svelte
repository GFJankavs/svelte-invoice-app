<script lang="ts">
    export let dark: boolean = false;
</script>

<button class="heading--s-variant {dark ? 'dark' : ''}">
    <slot />
</button>

<style>
    button {
        border: none;
        border-radius: 24px;
        padding: 16px 24px;
        background-color: #373b53;
        cursor: pointer;
        color: var(--color-6);
        display: flex;
        align-items: center;
        justify-content: center;
    }

    button:hover {
        background-color: var(--color-8);
    }

    button.dark {
        background-color: #373b53;
        color: var(--color-5);
    }

    button.dark:hover {
        background-color: var(--color-3);
    }
</style>
