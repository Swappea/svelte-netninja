<script>
  import Modal from "./Modal.svelte";
  import AddPersonForm from "./AddPersonForm.svelte";
  let people = [
    { name: "yoshi", beltColor: "black", age: 25, id: 1 },
    { name: "mario", beltColor: "orange", age: 45, id: 2 },
    { name: "luigi", beltColor: "brown", age: 33, id: 3 }
  ];

  let showModal = false;

  const toggleModal = () => {
    showModal = !showModal;
  };

  const handleClick = personId => {
    people = people.filter(person => person.id !== personId);
  };

  const addPerson = e => {
    const person = e.detail;
    people = [person, ...people];
    showModal = false;
  };

  let num = 3;
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<!-- {#if num > 20}ds sdds{:else if num > 5}ab sdsdds{:else}sdsdsdsd sdsdds{/if} -->

<Modal isPromo={true} {showModal} on:click={toggleModal}>
  <AddPersonForm on:addPerson={addPerson} />
</Modal>
<main>
  <button on:click={toggleModal}>Open Modal</button>
  <h1>People</h1>
  <div>
    {#each people as person (person.id)}
      <div>
        <h4>{person.name}</h4>
        {#if person.beltColor === 'black'}
          <p>
            <strong>Master Ninja</strong>
          </p>
        {/if}
        <p>{person.age} years old, {person.beltColor} belt.</p>
        <button on:click={() => handleClick(person.id)}>delete</button>
      </div>
    {:else}
      <p>There are no people to show...</p>
    {/each}
  </div>
</main>
