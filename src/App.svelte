<script>
  import NewMeetup from "./meetup/Form.svelte";

  import Header from "./components/Header.svelte";
  import MeetupGrid from "./components/molecules/MeetupGrid.svelte";
  import TextInput from "./components/elements/TextInput.svelte";
  import Button from "./components/elements/Button.svelte";

  let meetups = [
    {
      id: "1",
      title: "Creative Writing Workshop",
      tagline: "Find your own unique voice through writing",
      description:
        "An expert-led workshop focusing on the intricacies of style and tone in your writing.",
      imageURL:
        "https://stayfocusedwritersretreat.files.wordpress.com/2014/02/writing-pic1.jpg",
      location: "Dagger Mountain Roastery, Valparaiso, IN 46383",
      contactEmail: "test@writing.com",
      isFavorited: false,
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
      contactEmail: "test@coding.com",
      isFavorited: false,
    },
  ];

  let title = "";
  let tagline = "";
  let location = "";
  let imageURL = "";
  let contactEmail = "";
  let description = "";
  let mutateMeetups = null;

  const addMeetup = (event) => {
    console.log(event);

    const newMeetup = {
      id: Math.random().toString(),
      title: event.detail.title,
      tagline: event.detail.tagline,
      location: event.detail.location,
      imageURL: event.detail.imageURL,
      contactEmail: event.detail.contactEmail,
      description: event.detail.description,
      isFavorited: false,
    };

    meetups = [newMeetup, ...meetups];

    mutateMeetups = null;
  };

  const toggleFavorite = (event) => {
    console.log(event);
    const id = event.detail.id;
    const meetup = { ...meetups.find((meetup) => meetup.id === id) }; // this copies the object's key-value pairs w/ spread operator so we aren't mutating the original data with favoritedMeetup.

    meetup.isFavorited = !meetup.isFavorited;
    const meetupIndex = meetups.findIndex((meetup) => meetup.id === id);
    const updatedMeetups = [...meetups];
    updatedMeetups[meetupIndex] = meetup;
    meetups = updatedMeetups;
  };
</script>

<Header />
<body>

  {#if mutateMeetups === 'add'}
    <NewMeetup
      on:newMeetup={addMeetup}
      on:cancel={() => (mutateMeetups = null)} />
    <!-- <container class="transport">
      <Button content="Cancel" on:click={() => (mutateMeetups = null)} />
    </container> -->
  {:else}
    <container class="transport">
      <Button on:click={() => (mutateMeetups = 'add')}>+ Meetup</Button>
    </container>
  {/if}
  <MeetupGrid data={meetups} on:toggleFavorite={toggleFavorite} />
</body>

<style>
  body {
    padding-top: 6em;
    background: var(--Bastille);
    min-height: 100vh;
  }
  .transport {
    display: flex;
    justify-content: center;
  }
</style>
