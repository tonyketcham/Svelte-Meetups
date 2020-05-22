<script>
  import Header from "./components/Header.svelte";
  import MeetupItem from "./meetup/Item.meetup.svelte";

  const meetups = [
    {
      id: "1",
      title: "Creative Writing Workshop",
      tagline: "Find your own unique voice through writing",
      description:
        "An expert-led workshop focusing on the intricacies of style and tone in your writing.",
      imageURL:
        "https://stayfocusedwritersretreat.files.wordpress.com/2014/02/writing-pic1.jpg",
      location: "Dagger Mountain Roastery, Valparaiso, IN 46383",
      contactEmail: "test@writing.com"
    },
    {
      id: "2",
      title: "Creative Coding Workshop",
      tagline: "Make some funky shit",
      description:
        "An expert-led workshop focusing on the nature of code and simulating natural processes.",
      imageURL:
        "http://mediashift.org/wp-content/uploads/sites/8/2014/12/4696338852_bde479b169_o.jpg",
      location: "Uptown Cafe, Valparaiso, IN 46383",
      contactEmail: "test@coding.com"
    }
  ];
</script>

<Header />
<body>
  <div class="container">
    {#each meetups as meetup, index (meetup.id)}
      <MeetupItem {meetup} />
    {/each}
  </div>
</body>

<style>
  html {
    margin: 0;
    padding: 0;
  }
  body {
    margin: 0;
    background: #eee;
  }
  .container {
    display: flex;
    width: 75%;
    margin: auto;
  }
</style>
