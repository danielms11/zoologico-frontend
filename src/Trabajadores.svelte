<script>
  import { onMount, getContext } from "svelte";
  import { jsonData }            from "./store.js";

  import Buscar                  from "./Buscar.svelte";
  import Trabajador                 from "./Trabajador.svelte";
  import Boton                   from "./Boton.svelte";

  const URL = getContext("URL");

  let busqueda = "";
  let trabajador = {};

  onMount(async () => {
    const response = await fetch(URL.trabajadores);
    const data = await response.json();
    $jsonData = data;
  });

  $: regex = new RegExp(busqueda, "i");
  $: datos = busqueda 
    ? $jsonData.filter(item => regex.test(item.nombre))
    : $jsonData;

</script>

<h1>TRABAJADORES</h1>
<Buscar bind:busqueda />

<div class="container">
  <Trabajador bind:trabajador>
    <div style="text-align: right">
      <Boton documento={trabajador} tipo="insertar" coleccion="trabajadores" />
    </div>
  </Trabajador>
</div>

<div class="container">
  {#each datos as trabajador}
    <Trabajador {trabajador}>
      <div style="text-align: right">
        <Boton documento={trabajador} tipo="modificar" coleccion="trabajadores" />
        <Boton documento={trabajador} tipo="eliminar" coleccion="trabajadores" />
      </div>
    </Trabajador>
  {/each}
</div>

<style>
  .container {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: left;
    flex-wrap: wrap;
  }
</style>