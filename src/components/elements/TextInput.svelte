<script>
  export let label = null;
  export let id = null;
  export let value = null;
  export let controlType = null;
  export let required = false;
  export let type = null;
  export let rows = null;
</script>

<div class="form-control">
  <label for={id}>{label}</label>
  {#if controlType === 'textarea'}
    {#if required}
      <textarea {rows} {id} {value} on:input required />
    {:else}
      <textarea {rows} {id} {value} on:input />
    {/if}
  {:else if required}
    <input {type} {id} {value} on:input required />
  {:else}
    <textarea {rows} {id} {value} on:input />
  {/if}
</div>

<style>
  input,
  textarea {
    display: block;
    width: 100%;
    font: inherit;
    border: none;
    border-bottom: 2px solid #ccc;
    border-radius: 3px 3px 0 0;
    color: white;
    background: #2e273e;
    padding: 0.15rem 0.25rem;
    transition: border-color 0.1s ease-out;
  }

  input:focus,
  textarea:focus {
    border-color: #e40763;
    outline: none;
  }

  label {
    display: block;
    margin-bottom: 0.5rem;
    width: 100%;
    color: white;
  }

  .form-control {
    padding: 0.5rem 0;
    width: 100%;
    margin: 0.25rem 0;
  }
</style>
