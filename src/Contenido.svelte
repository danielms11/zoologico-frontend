<script>
  import { Route }  from "svelte-routing";
  import Inicio     from "./Inicio.svelte";
  import Animales  from "./Animales.svelte";
  import Trabajadores   from "./Trabajadores.svelte";
</script>

<main id="contenido">
  <Route path="/" component={Inicio} />
  <Route path="/animales" component={Animales} />
  <Route path="/trabajadores" component={Trabajadores} />
</main>

<style>
  main {
    padding: 20px;
    padding-top: 50px;
  }
</style>
