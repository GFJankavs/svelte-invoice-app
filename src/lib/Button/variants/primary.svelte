<script lang="ts">
    export let isDelete: boolean = false;
    import IconPlus from "../../icons/IconPlus.svelte";
    export let src: typeof IconPlus | undefined;
</script>

<button
    class="heading--s-variant {src ? 'withIcon' : ''} {isDelete
        ? 'delete'
        : ''}"
>
    {#if src}
        <div class="icon-plus">
            <svelte:component this={src} />
        </div>
    {/if}
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

    button.delete {
        background-color: var(--color-9);
    }

    button.delete:hover {
        background-color: var(--color-10);
    }

    button.withIcon {
        justify-content: flex-start;
        padding: 8px 18px 8px 8px;
        gap: 16px;
        min-width: 100px;
    }

    .icon-plus {
        width: 32px;
        height: 32px;
        background-color: white;
        border-radius: 32px;
        display: flex;
        align-items: center;
        justify-content: center;
    }
</style>
