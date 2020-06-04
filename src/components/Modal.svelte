<script>
  export let title = "Modal";

  import Button from "./Button.svelte";
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();
</script>

<div class="modal-backdrop" on:click={() => dispatch('cancel', true)} />
<div class="modal">
  <header>
    <Button mode="icon" on:click={() => dispatch('cancel', true)}>x</Button>
  </header>
  <h1>{title}</h1>
  <div class="content">
    <slot />
  </div>
  <footer>
    <slot name="footer" />
  </footer>
</div>

<style>
  .modal-backdrop {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background: rgba(0, 0, 0, 0.75);
    z-index: 10;
  }

  .modal {
    position: fixed;
    top: 10vh;
    left: 10%;
    width: 80%;
    max-height: 80vh;
    background: #201c29;
    border-radius: 15px;
    z-index: 100;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    /* overflow: scroll; */
  }

  header {
    display: flex;
    justify-content: flex-end;
    color: white;
    margin-top: 1rem;
  }

  h1 {
    color: white;
    padding: 1rem;
    margin: 0;
    text-align: center;
    font-family: "Roboto Slab", sans-serif;
  }

  .content {
    width: 66%;
    margin: auto;
    margin-bottom: 2rem;
  }

  footer {
    padding: 1rem;
  }

  @media (min-width: 768px) {
    .modal {
      width: 40rem;
      left: calc(50% - 20rem);
    }
  }
</style>
