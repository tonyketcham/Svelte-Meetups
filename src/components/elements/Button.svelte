<script>
  export let type = null;
  export let href = null;
  export let mode = null;
  export let style = null;
  export let newTab = null;

  import ButtonIcon from "./ButtonIcon.svelte";
</script>

{#if href}
  {#if mode === 'icon'}
    <ButtonIcon {href} {newTab} {style}>
      <slot>
        <p>icon goes here</p>
      </slot>
    </ButtonIcon>
  {:else if newTab}
    <a {href} target="_blank" rel="noopener noreferrer" class={style}>
      <slot>Link Button</slot>
    </a>
  {:else}
    <a {href} class={style}>
      <slot>Link Button</slot>
    </a>
  {/if}
{:else}
  {#if mode === 'icon'}
    <ButtonIcon {type} on:click {style}>
      <slot>
        <p>This slot should be filled!</p>
      </slot>
    </ButtonIcon>
  {:else}
    <button {type} on:click class={style}>
      <slot>Button</slot>
    </button>
  {/if}
{/if}

<style>
  button,
  a {
    font: inherit;
    font-weight: 600;
    border: 2px solid black;
    background: var(--Saffron-Mango);
    padding: 0.5rem 1rem;
    color: black;
    border-radius: 5px;
    box-shadow: 1px 1px 3px rgba(0, 0, 0, 0.26);
    cursor: pointer;
    text-decoration: none;
  }

  button:focus {
    outline: none;
  }

  button:hover,
  button:active,
  a:hover,
  a:active {
    background: #e40763;
    border: 2px solid black;
    box-shadow: 1px 1px 8px rgba(77, 51, 51, 0.26);
  }

  button:disabled,
  button:disabled:hover,
  button:disabled:active {
    background: #ccc;
    border-color: #ccc;
    color: #959595;
    box-shadow: none;
    cursor: not-allowed;
  }

  .success {
    background: #01a129;
    border-color: #01a129;
  }

  .success:hover,
  .success:active {
    background: #1ac745;
    border-color: #1ac745;
  }

  .outline {
    background: transparent;
    color: #cf0056;
    box-shadow: none;
  }

  .outline:hover,
  .outline:active {
    background: #ffc7de;
    box-shadow: none;
  }

  .outline:disabled,
  .outline:disabled:hover,
  .outline:disabled:active {
    background: transparent;
    color: #ccc;
  }

  .outline.success {
    border-color: #01a129;
    color: #01a129;
  }

  .outline.success:hover,
  .outline.success:active {
    background: #c2ffd1;
  }

  .spread {
    flex: auto;
    margin: 0 2rem;
  }
</style>
