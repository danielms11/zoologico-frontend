<script>
  import Boton from "./Boton.svelte";
  
  export let trabajador = {};
</script>

<div class="card" on:click>
  <input bind:value={trabajador.nombre} class="title" />
  <input bind:value={trabajador.apellidos} class="title" />
  <slot />
</div>

<style>
  .title {
    font-weight: bold;
  }
  .card {
    background-color: green;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    border-radius: 5px;
    transition: 0.3s;
    padding: 10px;
    margin: 10px;
  }

  .card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.4);
  }

  input {
    background-color: greenyellow;
    padding: 10px;
    font-size: 14px;
    color: black;
    border: 0;
    outline: none;
    margin-left: 5px;
    margin-bottom: 4px;
    max-width: 140px;
  }
  
  input:focus {
    background-color: white;
  }

  input:required:invalid,
  input:focus:invalid {
    background-color: lightpink;
  }
</style>
