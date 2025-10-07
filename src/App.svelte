<script>
  import Header from "./components/Header.svelte";
  import Footer from "./components/Footer.svelte";
  import { wrap } from "svelte-spa-router/wrap";
  import Router from "svelte-spa-router";

  // Import delle pagine
  import Home from "./routes/Home.svelte";
  import About from "./routes/About.svelte";
  import Contact from "./routes/Contact.svelte";

  // Mappa delle route
  const routes = {
    "/": wrap({ component: Home }),
    "/about": wrap({ component: About }),
    "/contact": wrap({ component: Contact })
  };
</script>

<div class="app">
  <Header />

  <main>
    <Router {routes} />
  </main>

  <Footer />
</div>

<style>
  :global(html, body) {
    margin: 0;
    padding: 0;
	  box-sizing: border-box;
  max-width: none;   /* niente sbordi */
    width: 100%;
  font-family: 'Poppins', sans-serif; /* usa Poppins */
    background: #fff;
    color: #111;
  }

  .app {
    width: 100%;
    max-width: none;   /* si adatta esattamente alla viewport */
    margin: 0 auto;     /* centra tutto se max-width < 100% */
    min-height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center; /* centra i contenuti orizzontalmente */
  }

  main {
    flex: 1;
    width: 100%;
    max-width: none;   /* opzionale: limite desktop */
    padding: 2rem 1vw;  /* padding relativo, non fisso */
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
</style>

