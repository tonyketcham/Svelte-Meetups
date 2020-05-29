<script>
  /**
   * A clickable button that has no intrinsic button styling but rather relies on
   * the input slot being an icon, or something else that should be clickable.
   *
   * @author Tony Ketcham (ketcham.dev@gmail.com)
   * */
  export let type = null;
  export let href = null;
  export let style = null;
  export let newTab = null;
</script>

{#if href && !newTab}
  <a {href} class={style}>
    <slot style="width: 100%;">
      <p>Default Button Icon</p>
    </slot>
  </a>
{:else if href && newTab}
  <a {href} target="_blank" rel="noopener noreferrer" class={style}>
    <slot style="width: 100%;">
      <p>Default Button Icon</p>
    </slot>
  </a>
{:else}
  <button {type} on:click class={style}>
    <slot style="width: 100%;">
      <p>Default Button Icon</p>
    </slot>
  </button>
{/if}

<style>
  button {
    width: 36pt;
    background: transparent;
    border: transparent;
    outline: none;
  }
  .icon {
    width: 45px;
  }

  .pink-outline {
    fill: #d75b61;
  }
</style>
