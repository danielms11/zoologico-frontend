<script>
  import { onMount, getContext } from "svelte";
  import { jsonData }            from "./store.js";

  import Buscar                  from "./Buscar.svelte";
  import Animal                from "./Animal.svelte";
  import Boton                   from "./Boton.svelte";

  const URL = getContext("URL");

  let busqueda = "";
  let animal = {};

  onMount(async () => {
    const response = await fetch(URL.animales);
    const data = await response.json();
    $jsonData = data;
  });

  $: datos = $jsonData.filter ( item => RegExp(busqueda, "i").test(item.nombre)) 

</script>

<h1>ANIMALES</h1>
<Buscar bind:busqueda />

<div class="container">
  <Animal bind:animal>
    <div style="text-align: right">
      <Boton documento={animal} tipo="insertar" coleccion="animales" />
    </div>
  </Animal>
</div>

<div class="container">
  {#each datos as animal}
    <Animal {animal}>
      <div style="text-align: right">
        <Boton documento={animal} tipo="modificar" coleccion="animales" />
        <Boton documento={animal} tipo="eliminar"  coleccion="animales" />
      </div>
    </Animal>
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
