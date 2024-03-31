<script lang="ts">
    import ButtonWithIcon from "./variants/withIcon.svelte";
    import ButtonWithLightAndDark from "./variants/withLightAndDark.svelte";
    import ButtonDarkVariant from "./variants/dark.svelte";

    export let withIcon: string | undefined = "";
    export let mode: "light" | "dark" | undefined = undefined;
</script>

{#if withIcon && withIcon.length > 0}
    <ButtonWithIcon src={withIcon}>
        <slot />
    </ButtonWithIcon>
{:else if mode}
    <ButtonWithLightAndDark {mode}>
        <slot />
    </ButtonWithLightAndDark>
{:else}
    <ButtonDarkVariant dark={mode === "dark"}>
        <slot />
    </ButtonDarkVariant>
{/if}

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
