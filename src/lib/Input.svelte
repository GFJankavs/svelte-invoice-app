<script lang="ts">
    export let label: string = "";
    export let value: string = "";
</script>

<div class="container">
    <span class="text--body-variant">{label}</span>
    <input type="text" {value} class="heading--s-variant" />
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        gap: 8px;
        width: 100%;
        max-width: 240px;
    }

    .container input {
        padding: 18px 20px 15px;
        color: var(--color-8);
        border-radius: 4px;
        border: 1px solid var(--color-5);
        width: 100%;
    }

    .container input:active {
        border: 1px solid var(--color-2);
    }
</style>
