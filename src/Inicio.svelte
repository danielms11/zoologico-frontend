<script>
  import { Link } from "svelte-routing";
</script>

<h1>Zoológico</h1>
<p>
  <small>
    Backend en
    <a href="https://zoologico.onrender.com/">
      https://zoologico.onrender.com/
    </a>
  </small>
</p>

<div class="bloque">
  <Link to="/">
    <div class="resumen">
      <span class="opcion"> Inicio</span>
      <span class="descripcion">Esta página de información.</span>
    </div>
  </Link>

  <Link to="/animales">
    <div class="resumen">
      <span class="opcion">🦁 Animales</span>
      <span class="descripcion">
        Gestión de animales
      </span>
    </div>
  </Link>

  <Link to="/trabajadores">
    <div class="resumen">
      <span class="opcion">👥 Trabajadores</span>
      <span class="descripcion">
        Gestión de trabajadores
      </span>
    </div>
  </Link>

</div>
<p>
  <small>
    <b>
      Código fuente en
      <a href="https://github.com/danielms11/zoologico-frontend.git">
        https://github.com/danielms11/zoologico-frontend.git
      </a>
    </b>
  </small>
</p>

<style>
  h1,
  div,
  p {
    padding: 3px;
    color: white;
  }
  div {
    padding: 30px;
  }
  a {
    color: aqua;
  }
  .bloque {
    display: flex;
    flex-direction: column;
  }
  .resumen {
    display: flex;
    flex-wrap: wrap;    
    padding: 5px;
    margin: 0 0 15px;
    border: 1px solid #000;
    border-radius: 4px;
    box-shadow: 0 0 3px rgba(0, 0, 0, 0.19);
    border: 1px solid rgb(245, 177, 31);
    border-radius: 4px;
  }

  .opcion {
    display: flex;   
    word-break: break-word;
    padding: 0 10px;
    font-size: 14px;
    font-weight: 700;
    text-shadow: 0 1px 0 rgba(0, 0, 0, 0.1);
    font-family: sans-serif;
    color: black;
    border-radius: 4px;
    background: greenyellow;
    min-width: 140px;
    padding: 10px;
  }

  .descripcion {
    font-size: 14px;
    flex: 1 1 auto;
    word-break: break-word;
    font-family: sans-serif;
    color: black;
    padding-top: 10px;
    padding-left: 10px;
    background-color: green;
  }
</style>
