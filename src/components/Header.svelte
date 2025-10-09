<script>
  import ActiveDays from "./ActiveDays.svelte";
  import logo from "../assets/logo.png";
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

    <!-- Logo (assoluto, sempre centrato) -->
    <h1 class="logo">
      <a href="/" use:link>
        <img src={logo} alt="robe logo" class="logo-img" />
      </a>
    </h1>

    <!-- Menu (destra) -->
    <button class="menu-btn" on:click={() => menuOpen = !menuOpen}>
      MENU
    </button>
  </div>
</nav>

<!-- Overlay menu -->
<div class="overlay {menuOpen ? 'open' : ''}">
  <button class="close-btn" on:click={() => menuOpen = false}>×</button>
  <ul>
    <li><a href="/about" use:link on:click={() => menuOpen = false}>ABOUT</a></li>
    <li><a href="/contact" use:link on:click={() => menuOpen = false}>CONTACT</a></li>
  </ul>
</div>

<style>
  /* ===== Desktop ===== */
  .header {
    position: fixed;
    top: 0; left: 0; width: 100%;
    backdrop-filter: blur(12px);
    background: rgba(255,255,255,0.6);
    border-bottom: 1px solid rgba(0,0,0,0.05);
    z-index: 1000;
    display: flex; justify-content: center;
  }

  .inner {
    position: relative;                /* logo assoluto si posiziona qui */
    width: 100%; max-width: 1400px;
    margin: 0 auto; padding: 1rem 5vw;

    display: flex;
    justify-content: space-between;    /* ActiveDays e MENU ai lati */
    align-items: center;
  }

  /* ActiveDays */
  .active-days-wrapper {
    flex: 0 0 auto;   /* non cresce né si restringe */
    min-width: 150px; /* spazio fisso: evita che i numeri spostino tutto */
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
    transition: transform 0.3s ease;
  }
  .logo-img:hover { transform: scale(1.05) rotate(-3deg); }

  /* Menu */
.menu-btn {
  background: none;
  border: none;
  cursor: pointer;
  font-family: "Poppins", sans-serif;
  font-weight: 800;
  font-size: 1.1rem;
  letter-spacing: 0.05em;
  color: #111;
  position: relative;
  overflow: hidden;
  transition: color 0.3s ease, transform 0.2s ease;
}

.menu-btn:hover {
  color: #ff4f70;
  transform: translateY(-2px);
}

.menu-btn::after {
  content: "";
  position: absolute;
  bottom: -2px; left: 0;
  width: 100%; height: 2px;
  background: currentColor;
  transform: scaleX(0);
  transform-origin: right;
  transition: transform 0.3s ease;
}

.menu-btn:hover::after {
  transform: scaleX(1);
  transform-origin: left;
}


  /* Overlay menu */
  .overlay {
    position: fixed; inset: 0;
    background: #111;
    color: #fff;
    display: flex; flex-direction: column;
    justify-content: center; align-items: center;
    opacity: 0; pointer-events: none;
    transition: opacity 0.4s ease;
    z-index: 2000;
  }
  .overlay.open { opacity: 1; pointer-events: auto; }

  .overlay .close-btn {
    position: absolute; top: 1.5rem; right: 1.5rem;
    background: none; border: none;
    font-size: 2rem; cursor: pointer; color: #fff;
  }

  .overlay ul {
    list-style: none; margin: 0; padding: 0;
    display: flex; flex-direction: column; gap: 2rem;
    font-size: 2rem; font-weight: 700;
  }
  .overlay a {
    color: #fff; text-decoration: none;
    transition: color 0.3s;
  }
  .overlay a:hover { color: #ff4f70; }
  
  /* ActiveDays in pillola */
.active-days-wrapper {
  flex: 0 0 auto;          /* non cresce né si restringe */
  min-width: 150px;        /* spazio fisso: evita che i numeri spostino il resto */
  /*background: linear-gradient(90deg, #ff4f70, #ff914d);*/
  background: #fff;
  /*color: #fff;*/
    color: #000;
  padding: 0.4rem 1rem;
  border-radius: 999px;
  font-weight: bold;
  font-size: 0.85rem;
  box-shadow: 0 3px 8px rgba(0,0,0,0.15);
  transition: transform 0.2s;
  justify-self: start;
}
.active-days-wrapper:hover {
  transform: scale(1.05);
}


  /* ===== Mobile ===== */
  @media (max-width: 640px) {
    .header { position: static; }
    .inner {
      position: static; flex-direction: column; gap: 1rem;
      padding: 2.5rem 5vw 1rem; text-align: center;
    }

    .active-days-wrapper {
      min-width: auto;
      justify-self: center;
    }

    .logo {
      position: static;
      transform: none;
    }
    .logo-img { width: 60%; margin: 0 auto; }

    .menu-btn {
      margin-top: 0.5rem;
      font-size: 1rem;
    }
  }
</style>
