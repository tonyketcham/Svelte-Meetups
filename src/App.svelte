<script>
  import TextInput from "./components/TextInput.svelte";

  import Header from "./components/Header.svelte";
  import MeetupGrid from "./meetup/Grid.svelte";

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

  let title = "";
  let tagline = "";
  let location = "";
  let imageURL = "";
  let contactEmail = "";
  let description = "";

  const addMeetup = () => {
    const newMeetup = {
      id: Math.random().toString(),
      title: title,
      tagline: tagline,
      location: location,
      imageURL: imageURL,
      contactEmail: contactEmail,
      description: description
    };

    meetups = [newMeetup, ...meetups];
  };
</script>

<Header />
<body>
  <form on:submit|preventDefault={addMeetup}>
    <TextInput
      id="title"
      label="Title"
      type="text"
      value={title}
      on:input={event => (title = event.target.value)} />
    <TextInput
      id="tagline"
      label="Tagline"
      type="text"
      value={tagline}
      on:input={event => (tagline = event.target.value)} />
    <TextInput
      id="location"
      label="Location"
      type="text"
      value={location}
      on:input={event => (location = event.target.value)} />
    <TextInput
      id="imageURL"
      label="Image URL"
      type="text"
      value={imageURL}
      on:input={event => (imageURL = event.target.value)} />
    <TextInput
      id="contactEmail"
      label="Contact Email"
      type="email"
      value={contactEmail}
      on:input={event => (contactEmail = event.target.value)} />
    <TextInput
      id="description"
      label="Description"
      controlType="textarea"
      rows="3"
      value={description}
      on:input={event => (description = event.target.value)} />

    <button type="submit">Publish</button>

  </form>
  <MeetupGrid {meetups} />
</body>

<style>
  body {
    padding-top: 6em;
    background: #201c29;
  }
</style>
