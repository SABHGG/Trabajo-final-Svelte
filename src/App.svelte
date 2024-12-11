<script>
  import { Router, Link, Route } from "svelte-routing";
  import ParImpar from "./view/parImpar.svelte";
  import Paises from "./view/paises.svelte";
  import ApiMorty from "./view/apimorty.svelte";
</script>

<main>
  <Router>
    <nav>
      <Link to="/">Par o Impar</Link>
      <Link to="/paises">Paises</Link>
      <Link to="/rickandmorty">Api Rick and Morty</Link>
    </nav>

    <Route path="/">
      <ParImpar></ParImpar>
    </Route>
    <Route path="/paises">
      <Paises></Paises>
    </Route>
    <Route path="/rickandmorty">
      <ApiMorty></ApiMorty>
    </Route>
  </Router>
</main>

<style>
</style>
