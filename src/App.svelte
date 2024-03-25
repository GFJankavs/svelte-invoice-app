<script lang="ts">
import Button from "./lib/Button.svelte";
import PlusIcon from "./assets/icon-plus.svg";
</script>

<main>
  <Button>
    <img src={PlusIcon} alt="plus icon" slot="icon"/>
    Click me
  </Button>
</main>
<style>

</style>
