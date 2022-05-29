<script>
  import { Column } from "carbon-components-svelte";

  export let shown = false;

  export const show = () => {
    shown = !shown;
  };
</script>

{#if shown}
  <Column>
    <slot />
  </Column>
{/if}
