<script>
  import ActiveDays from "./ActiveDays.svelte";
  import logo from "../assets/logo.png";
  import menuIcon from "../assets/menu.png";
  import about from "../assets/about.png";
  import contatti from "../assets/contatti.png";
  import { link } from "svelte-spa-router";

  let menuOpen = false;
</script>

<nav class="header">
  <div class="inner">
    <!-- ActiveDays (sinistra) -->
    <div class="active-days-wrapper">
      <ActiveDays />
    </div>

    <!-- Logo (centrato assoluto, non si sposta mai) -->
    <h1 class="logo">
      <a href="/" use:link>
        <img src={logo} alt="robe logo" class="logo-img" />
      </a>
    </h1>

    <!-- “?” (destra) -->
    <button class="menu-btn" on:click={() => menuOpen = !menuOpen}>
      <img src={menuIcon} alt="Apri menu" class="menu-icon" />
    </button>
  </div>
</nav>

<!-- Off-canvas (da destra) -->
<div class="offcanvas {menuOpen ? 'open' : ''}">
  <button class="close-btn" on:click={() => menuOpen = false}>×</button>
  <ul>
    <li>
      <a href="/about" use:link on:click={() => menuOpen = false}>
        <img src={about} alt="About" />
      </a>
    </li>
    <li>
      <a href="/contact" use:link on:click={() => menuOpen = false}>
        <img src={contatti} alt="Contact" />
      </a>
    </li>
  </ul>
</div>

<style>
  /* ===== Desktop ===== */
  .header {
    position: fixed;
    top: 0; left: 0; width: 100%;
    background: #fff;
    border-bottom: 1px solid #eee;
    z-index: 1000;
    display: flex; justify-content: center;
  }

  .inner {
    position: relative;                /* per il logo assoluto */
    width: 100%; max-width: 1400px;
    margin: 0 auto;
    padding: 1rem 5vw;

    display: flex;
    align-items: center;
    justify-content: space-between;    /* ActiveDays a sx, ? a dx */
  }

  /* ActiveDays: non influenza più il logo */
  .active-days-wrapper {
    flex: 0 0 auto;        /* niente shrink/grow */
    min-width: 0;          /* lascia adattare senza spingere */
  }

  /* Logo assoluto al centro */
  .logo {
    position: absolute;
    left: 50%; transform: translateX(-50%);
    margin: 0; text-align: center;
    pointer-events: auto;
  }
  .logo-img {
    width: clamp(90px, 8vw, 140px);
    height: auto; display: block; margin: 0 auto;
  }

  /* “?” a destra */
  .menu-btn {
    background: none; border: none; cursor: pointer; padding: 0;
    flex: 0 0 auto;
  }
  .menu-icon {
    width: clamp(28px, 4vw, 60px);
    height: auto; display: block;
  }

  /* Off-canvas da destra */
  .offcanvas {
    position: fixed; top: 0; right: -300px;
    width: 300px; height: 100vh; background: #fff;
    box-shadow: -2px 0 10px rgba(0,0,0,.15);
    transition: right .3s ease; z-index: 2000;
    padding: 2rem 1.5rem; box-sizing: border-box;
  }
  .offcanvas.open { right: 0; }

  .offcanvas .close-btn {
    position: absolute; top: 1rem; right: 1rem;
    background: none; border: none; font-size: 2rem; cursor: pointer;
    color: #000; z-index: 2100;
  }

  .offcanvas ul {
    list-style: none; margin: 0; padding: 4rem 0 0;
    display: flex; flex-direction: column; gap: 2rem;
  }

  .offcanvas li img { width: 120px; height: auto; display: block; }

  /* ===== Mobile ===== */
  @media (max-width: 640px) {
    .header { position: static; }              /* scorre via */
    .inner {
      position: static;                        /* logo torna normale */
      flex-direction: column; gap: 1rem;
      padding: 2rem 5vw; text-align: center;
    }

    .logo { position: static; transform: none; }
    .logo-img { width: 60%; }

    .menu-icon { width: 60px; }
  }
</style>
