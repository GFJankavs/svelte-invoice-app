<script lang="ts">

</script>

<button class="heading--s-variant">
    <slot name="icon"/>
    <slot></slot>
</button>

<style>
    button {
        border: none;
        border-radius: 24px;
        padding: 16px 24px;
        background-color: var(--color-1);
        cursor: pointer;
        color: #fff;
    }

    button:hover {
        background-color: var(--color-2);
    }
</style>