<script>
  let caracteres = [];
  let pagina = 1;
  async function loadCaracter() {
    const response = await fetch(
      `https://rickandmortyapi.com/api/character/?page=${pagina}`
    );
    const data = await response.json();
    caracteres = data.results;
  }
  loadCaracter();

  function nextPage() {
    pagina++;
    loadCaracter();
  }

  function prevPage() {
    if (pagina > 1) {
      pagina--;
      loadCaracter();
    }
  }
</script>

<svelte:head>
  <title>Personajes de Rick and Morty</title>
</svelte:head>

<main>
  <h1>Personajes de Rick and Morty</h1>
  <h2>pagina: {pagina}</h2>
  <section>
    {#each caracteres as character}
      <article class="card">
        <img src={character.image} alt={character.name} />
        <h2>{character.name}</h2>
        <h3>{character.species}</h3>
        <p>{character.status}</p>
      </article>
    {/each}
  </section>
  <div>
    <button on:click={prevPage}>Anterior</button>
    <button on:click={nextPage}>Siguiente</button>
  </div>
</main>

<style>
  section {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1rem;
    margin-bottom: 20px;
  }
  .card {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    img {
      width: 100%;
      border-radius: 5px 5px 0 0;
    }
    h2 {
      margin: 2px;
    }
    h3 {
      margin: 2px;
    }
    p {
      margin: 2px;
    }
  }
  div {
    display: flex;
    justify-content: center;
    gap: 20px;
  }
</style>
