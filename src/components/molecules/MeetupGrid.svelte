<script>
  import MeetupCard from "../../meetup/Card.svelte";

  // Iterable data in the form of an array or JSON object
  export let data = [] | {};
</script>

<section>
  <div class="container">
    {#each data as datum, index (datum.id)}
      <MeetupCard data={datum} on:toggleFavorite />
    {/each}
  </div>
</section>

<style>
  .container {
    display: grid;
    width: 75%;
    margin: auto;
  }
</style>
