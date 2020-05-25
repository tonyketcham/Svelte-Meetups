<script>
  import MeetupCard from "./Card.svelte";

  export let meetups = [];
</script>

<section>
  <div class="container">
    {#each meetups as meetup, index (meetup.id)}
      <MeetupCard {meetup} />
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
