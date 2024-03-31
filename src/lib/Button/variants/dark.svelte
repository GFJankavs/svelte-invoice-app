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
        background-color: var(--color-1);
        cursor: pointer;
        color: #fff;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    button:hover {
        background-color: var(--color-2);
    }
</style>
