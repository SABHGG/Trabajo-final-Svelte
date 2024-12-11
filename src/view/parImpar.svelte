<script>
  let numero = 0;
  let resultado;
  $: if (numero == 0) {
    resultado = "Neutro";
  } else if (numero % 2 === 0) {
    resultado = "Par";
  } else {
    resultado = "Impar";
  }
  const ListenInput = (event) => (numero = event.target.value);
</script>

<!-- Las variables las llamamos entre llaves-->
<div>
  <h1>Par o Impar</h1>
  <p>el numero es {numero} y es {resultado}</p>
  <input value={numero} type="number" on:input={ListenInput} />
</div>

<style>
  p {
    color: blue;
    font-size: 25px;
  }
</style>
