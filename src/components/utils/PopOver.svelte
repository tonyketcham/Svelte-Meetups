<script>
  import { onMount } from "svelte";

  let rootEl;

  onMount(() => {
    document.getElementById("pops").appendChild(rootEl);
  });
  rootEl = rootEl;
</script>

<div class="pop-over" bind:this={rootEl}>
  <slot />
</div>

<style>
  .pop-over {
    position: absolute;
    z-index: 100;
  }
</style>
