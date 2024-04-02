<script lang="ts">
    import Dropdown from "./lib/Dropdown.svelte";

    const dropdownOptions = [
        { value: "option1", label: "Option 1" },
        { value: "option2", label: "Option 2" },
        { value: "option3", label: "Option 3" },
    ];
</script>

<main>
    <div>
        <Dropdown options={dropdownOptions} />
    </div>
</main>

<style scoped>
</style>
