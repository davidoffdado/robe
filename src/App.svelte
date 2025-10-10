<script>
  import Header from "./components/Header.svelte";
  import Footer from "./components/Footer.svelte";
  import { wrap } from "svelte-spa-router/wrap";
  import Router from "svelte-spa-router";
  import Home from "./routes/Home.svelte";
  import About from "./routes/About.svelte";
  import Contact from "./routes/Contact.svelte";
  import Seguici from "./routes/Seguici.svelte";
  

  const routes = {
    "/": wrap({ component: Home }),
    "/about": wrap({ component: About }),
    "/contact": wrap({ component: Contact }),
	"/seguici": wrap({ component: Seguici })
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
    font-family: "Poppins", sans-serif;
    background: #fff;
    color: #111;
    overflow-y: scroll; /* evita micro-movimenti tra pagine corte/lunghe */
  }

 <!-- main {
  padding: 8rem 5vw 3rem;
  } -->
  
@media (max-width: 640px) {
  main {
    padding-top: 1rem; /* oppure 11rem/12rem, dipende dall’altezza del tuo header */
  }
}

</style>
