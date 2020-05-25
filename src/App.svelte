<script>
  import Header from "./components/Header.svelte";
  import MeetupGrid from "./meetup/Grid.svelte";

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
  <MeetupGrid {meetups} />
</body>

<style>
  body {
    padding-top: 6em;
    background: #201c29;
  }
</style>
