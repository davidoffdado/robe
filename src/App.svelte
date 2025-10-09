<script>
  import Header from "./components/Header.svelte";
  import Footer from "./components/Footer.svelte";
  import { wrap } from "svelte-spa-router/wrap";
  import Router from "svelte-spa-router";
  import Home from "./routes/Home.svelte";
  import About from "./routes/About.svelte";
  import Contact from "./routes/Contact.svelte";

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
    font-family: "Poppins", sans-serif;
    background: #fff;
    color: #111;

    overflow-y: scroll; /* evita micro-movimenti tra pagine corte/lunghe */

  }

  .app {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  main {
    flex: 1;
    display: flex;
    justify-content: center;
    box-sizing: border-box;
    padding: 8rem 5vw 3rem; /* spazio per l’header */
  }

@media (max-width: 640px) {
  main {
    padding-top: 1rem; /* oppure 11rem/12rem, dipende dall’altezza del tuo header */
  }
}

</style>
