<script lang="ts">
    import IconPlus from "../icons/IconPlus.svelte";
    import ButtonPrimary from "./variants/primary.svelte";
    import ButtonSecondary from "./variants/secondary.svelte";
    import ButtonTertiary from "./variants/tertiary.svelte";
    import ButtonLong from "./variants/long.svelte";

    export let variant: "primary" | "secondary" | "tertiary" | "long" =
        "primary";
    export let src: typeof IconPlus | undefined = undefined;
    export let mode: "light" | "dark" | undefined = undefined;
    export let isDelete: boolean = false;
</script>

{#if variant === "primary"}
    <ButtonPrimary {src} {isDelete}>
        <slot />
    </ButtonPrimary>
{:else if variant === "secondary"}
    <ButtonSecondary {mode}>
        <slot />
    </ButtonSecondary>
{:else if variant === "tertiary"}
    <ButtonTertiary dark={mode === "dark"}>
        <slot />
    </ButtonTertiary>
{:else if variant === "long"}
    <ButtonLong>
        <slot />
    </ButtonLong>
{/if}
