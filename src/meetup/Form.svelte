<script>
  import TextInput from "../components/elements/TextInput.svelte";
  import Button from "../components/elements/Button.svelte";
  import Modal from "../components/Modal.svelte";
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  let title = null;
  let tagline = null;
  let location = null;
  let imageURL = null;
  let contactEmail = null;
  let description = null;

  let meetup = {
    title: "title",
    tagline: "tagline",
    location: "location",
    imageURL: "imageURL",
    contactEmail: "contactEmail",
    description: "description",
  };
</script>

<Modal title="Publish a Meetup" on:cancel>
  <form on:submit|preventDefault={() => dispatch('newMeetup', meetup)}>
    <TextInput
      id="title"
      label="Title"
      type="text"
      value={title}
      on:input={(event) => (meetup.title = event.target.value)}
      required />
    <TextInput
      id="tagline"
      label="Tagline"
      type="text"
      value={tagline}
      on:input={(event) => (meetup.tagline = event.target.value)}
      required />
    <TextInput
      id="location"
      label="Location"
      type="text"
      value={location}
      on:input={(event) => (meetup.location = event.target.value)}
      required />
    <TextInput
      id="imageURL"
      label="Image URL"
      type="text"
      value={imageURL}
      on:input={(event) => (meetup.imageURL = event.target.value)}
      required />
    <TextInput
      id="contactEmail"
      label="Contact Email"
      type="email"
      value={contactEmail}
      on:input={(event) => (meetup.contactEmail = event.target.value)}
      required />
    <TextInput
      id="description"
      label="Description"
      controlType="textarea"
      rows="3"
      value={description}
      on:input={(event) => (meetup.description = event.target.value)}
      required />

    <Button type="submit">Publish</Button>
    <Button on:click={() => dispatch('cancel', true)}>Cancel</Button>
  </form>
</Modal>
