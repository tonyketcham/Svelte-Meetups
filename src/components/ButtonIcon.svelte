<script>
  export let type;
  export let href;
  export let style;
</script>

{#if href}
  <a {href} class={style}>
    <slot style="width: 100%;">
      <p>Default Button Icon</p>
    </slot>
  </a>
{:else}
  <button {type} class={style}>
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
  }
  .icon {
    width: 45px;
  }

  .pink-outline {
    fill: #d75b61;
  }
</style>
