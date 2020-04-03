<script>
  let firstName = "John";
  let lastName = "Doe";
  let beltColor = "black";

  $: fullName = `${firstName} ${lastName}`;

  $: {
    console.log(beltColor);
    console.log(fullName);
  }

  const handleClick = () => {
    beltColor = "orange";
  };
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

<main>
  <p>{fullName} - {beltColor} belt</p>

  <input type="text" bind:value={firstName} />
  <input type="text" bind:value={lastName} />

  <input type="text" bind:value={beltColor} />
</main>
