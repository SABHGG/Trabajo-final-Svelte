<script>
  const paises = {
    colombia: [
      "Colombia",
      "Bogotá",
      "51,52 millones",
      "Peso Colombiano",
      "1,142 millones de km²",
      "co",
    ],
    venezuela: [
      "Venezuela",
      "Caracas",
      "28,52 millones",
      "Bolívar",
      "916,445 km²",
      "ve",
    ],
    peru: [
      "Perú",
      "Lima",
      "32,51 millones",
      "Sol",
      "1,285 millones de km²",
      "pe",
    ],
    ecuador: [
      "Ecuador",
      "Quito",
      "17,08 millones",
      "Dólar",
      "283,561 km²",
      "ec",
    ],
    brasil: [
      "Brasil",
      "Brasilia",
      "209,5 millones",
      "Real",
      "8,515 millones de km²",
      "br",
    ],
    argentina: [
      "Argentina",
      "Buenos Aires",
      "45,38 millones",
      "Peso Argentino",
      "2,78 millones de km²",
      "ar",
    ],
  };
  let p = ["colombia", "venezuela", "peru", "ecuador", "brasil", "argentina"];
</script>

<svelte:head>
  <title>Paises de sudamerica</title>
</svelte:head>

<main>
  <section>
    {#each p as pais}
      <div class="col1">
        <img
          src={`https://flagcdn.com/w320/${paises[pais][5]}.png`}
          alt={`Bandera de ${paises[pais][0]}`}
        />
      </div>
      <div class="col2">
        <strong>{paises[pais][0]}</strong>
        <div class="linea">Capital: {paises[pais][1]}</div>
        <div class="linea">Población: {paises[pais][2]}</div>
        <div class="linea">Moneda: {paises[pais][3]}</div>
        <div class="linea">Área: {paises[pais][4]}</div>
      </div>
    {:else}
      <p>No hay paises</p>
    {/each}
  </section>
</main>

<style>
  main {
    display: grid;
    place-content: center;
  }
  section {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 5px;
    grid-auto-rows: minmax(100px, auto);
    border-radius: 10px;
    border-style: solid;
    border-color: black;
    border-width: 2px;
    width: max-content;
    place-content: center;
    padding: 12px;
  }
  .col1 {
    display: flex;
    aspect-ratio: 16/12;
    img {
      width: 288.425px;
      height: 191.988px;
    }
  }
  .col2 {
    display: flex;
    flex-direction: column;
    text-align: left;
  }
  strong {
    font-weight: bold;
    font-size: 24px;
  }
  .linea {
    font-size: 20px;
    margin-bottom: 12px;
  }
</style>
