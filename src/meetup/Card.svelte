<script>
  export let meetup = [];
  export let borderColors = ["#daae51", "#d53369"];

  import Button from "../components/Button.svelte";
  import { createEventDispatcher } from "svelte";
  import Badge from "../components/Badge.svelte";

  const randomColor = () => {
    return borderColors[Math.floor(Math.random() * borderColors.length)];
  };

  const dispatch = createEventDispatcher();
</script>

<article style="border-left: 2px solid {randomColor()}">
  <header>
    <h1>{meetup.title}</h1>
    <div class="details">
      <!-- <div class="badge">
        <Badge />
      </div> -->

      <h2>{meetup.tagline}</h2>
      <h3>{meetup.location}</h3>
    </div>
  </header>
  <div class="image" style="--imageURL: url({meetup.imageURL});" />
  <div class="content">
    <p>{meetup.description}</p>
  </div>
  <footer>
    <Button href="mailto:{meetup.contactEmail}" content="Email" />
    <Button style="spread" type="button" content="Details" />
    <Button
      mode="icon"
      on:click={() => dispatch('toggleFavorite', { id: meetup.id })}>
      <slot>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
          {#if meetup.isFavorited}
            <path
              fill="#d75b61"
              stroke="#d75b61"
              d="M469.6 80.7c-55.7-53-146.3-53-202 0l-11.6 11
              -11.6-11c-55.7-53-146.3-53-202 0C15.1 106.7 0 141.2 0 177.9c0 36.6
              15.1 71.1 42.4 97.2l201.2 191c3.5 3.3 7.9 4.9 12.4 4.9 4.4 0
              8.9-1.6 12.4-4.9l201.2-191C496.9 249 512 214.5 512 177.9 512 141.2
              496.9 106.7 469.6 80.7zM444.8 249L256 428.3 67.2 249C47 229.8 35.9
              204.6 35.9 177.9s11.1-52 31.2-71.1c21-20 48.6-30 76.2-30 27.6 0
              55.2 10 76.3 30l24 22.8c6.9 6.6 17.8 6.6 24.8 0l24-22.8c42-40
              110.4-40 152.5 0 20.1 19.2 31.2 44.4 31.2 71.1S465 229.8 444.8
              249z" />
          {:else}
            <path
              fill="white"
              stroke="white"
              stroke-width="1"
              d="M469.6 80.7c-55.7-53-146.3-53-202 0l-11.6 11
              -11.6-11c-55.7-53-146.3-53-202 0C15.1 106.7 0 141.2 0 177.9c0 36.6
              15.1 71.1 42.4 97.2l201.2 191c3.5 3.3 7.9 4.9 12.4 4.9 4.4 0
              8.9-1.6 12.4-4.9l201.2-191C496.9 249 512 214.5 512 177.9 512 141.2
              496.9 106.7 469.6 80.7zM444.8 249L256 428.3 67.2 249C47 229.8 35.9
              204.6 35.9 177.9s11.1-52 31.2-71.1c21-20 48.6-30 76.2-30 27.6 0
              55.2 10 76.3 30l24 22.8c6.9 6.6 17.8 6.6 24.8 0l24-22.8c42-40
              110.4-40 152.5 0 20.1 19.2 31.2 44.4 31.2 71.1S465 229.8 444.8
              249z" />
          {/if}
        </svg>
      </slot>
    </Button>

  </footer>

</article>

<style>
  article {
    width: 510px;
    margin: 1em auto;
    padding: 1em 2em;
    border-radius: 15px;
    color: #fff;
    background: #201c29;
    box-shadow: 0 2px 12px rgba(0, 0, 0, 0.36);
    position: relative;
    overflow: hidden;
    display: flex;
    flex-direction: column;
  }
  header {
    position: absolute;
    left: 0;
    width: inherit;
    justify-content: space-between;
    padding: 1em 2em;
    display: flex;
  }
  .details {
    text-align: right;
    display: flex;
    flex-direction: column;
    width: max-content;
    justify-content: center;
  }
  h1,
  h2,
  h3 {
    text-shadow: 0px 2px 20px rgba(0, 0, 0, 0.98);
    margin: 0;
  }
  h1 {
    font-size: 30pt;
    font-family: Helvetica, sans-serif;
    max-width: 45%;
  }
  h2 {
    font-size: 13pt;
    font-weight: 400;
    color: rgb(255, 234, 226);
    margin-bottom: 1rem;
    text-transform: uppercase;
  }
  h3 {
    font-size: 10pt;
    font-weight: 300;
    opacity: 0.85;
  }
  .image {
    height: 12rem;
    margin: -1em -2em 0.5em;
    overflow: hidden;
    background-image: linear-gradient(
        to bottom,
        rgba(23, 13, 29, 0.42) 25%,
        #201c29
      ),
      var(--imageURL);
    background-repeat: no-repeat;
    background-size: cover;
  }
  footer {
    display: flex;
    padding: 1rem 0 0.5rem;
  }
</style>
