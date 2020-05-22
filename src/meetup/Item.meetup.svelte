<script>
  export let meetup = [];
</script>

<article>
  <header>
    <h1>{meetup.title}</h1>
    <h2>{meetup.tagline}</h2>
    <h3>{meetup.location}</h3>
  </header>
  <div class="image" style="--imageURL: url({meetup.imageURL});" />
  <div class="content">
    <p>{meetup.description}</p>
  </div>
  <footer>
    <button>Show Details</button>
    <button>Favorite</button>
  </footer>

</article>

<style>
  article {
    max-width: 400px;
    margin: 50px auto;
    padding: 0 1em;
    border: 3px solid #333;
    border-radius: 15px;
    background: #fff;
    position: relative;
    overflow: hidden;
    display: flex;
    flex-direction: column;
  }
  header {
    position: absolute;
    left: 0;
    color: #fff;
    justify-content: center;
    padding: 0 1rem;
    display: flex;
  }
  h1,
  h2,
  h3 {
    text-shadow: 0px 0px 6px rgba(0, 0, 0, 0.48);
    margin: 0;
  }
  h1 {
    font-size: 30pt;
    font-family: Helvetica, sans-serif;
  }
  h2 {
    font-size: 12pt;
    font-weight: 300;
  }
  h3 {
    font-size: 8pt;
    font-weight: 300;
    opacity: 0.85;
  }
  .image {
    height: 12rem;
    background-color: #eee;
    margin: 0 -1em;
    overflow: hidden;
    background-image: linear-gradient(
        to bottom,
        rgba(23, 13, 29, 0.42) 25%,
        rgba(75, 108, 121, 0.93)
      ),
      var(--imageURL);
    background-repeat: no-repeat;
    background-size: cover;
  }
</style>
