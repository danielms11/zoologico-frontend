<script>
  import { Link } from "svelte-routing";
</script>

<nav>
  <ul class="menu">
    <li class="logo">
      <Link to="/">
        <span class="inicio"></span>
      </Link>
    </li>
    <li class="item active">
      <Link to="/animales">
        <span class="animales">🦁</span>
      </Link>
    </li>
    <li class="item active">
      <Link to="/trabajadores">
        <span class="trabajadores">👥</span>
      </Link>
    </li>
  </ul>
</nav>

<style>
  
  * {
    box-sizing: border-box;
  }

  nav {
    background: green;
    padding: 8px;
    position: -webkit-sticky; 
    position: sticky;
    top: 0;
    width: 100%;
  }

  ul {
    list-style-type: none;
  }

  span {
    padding-right: 10px;
  }

  .menu li:hover {
    text-shadow: 3px 3px 4px #6f6f70;
  }

  .menu li {
    font-weight: bold;
    font-size: 16px;
    padding: 15px 15px;
    white-space: nowrap;
  }

  /* Móvil */
  .menu {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .logo {
    flex: 1;
  }
  .item {
    order: 1;
    display: block;
    width: auto;
  }
  .active {
    display: block;
  }
  /* Tablet */
  @media all and (min-width: 600px) {
    .menu {
      justify-content: space-between;
    }
    .logo {
      flex: 1;
    }
    .item {
      order: 1;
      display: block;
      width: auto;
    }

    .inicio::after,
    .animales::after,
    .trabajadores::after {
      display: inline-block;
      padding-left: 10px;
    }

    .inicio::after {
      content: "Inicio";
    }
    .animales::after {
      content: "Animales";
    }
    .trabajadores::after {
      content: "Trabajadores";
    }
  }
  /* PC */
  @media all and (min-width: 900px) {
    .item {
      order: 1;
      display: block;
      width: auto;
    }
    .logo {
      order: 0;
    }
    .menu li {
      padding: 15px 10px;
    }
  }
</style>
