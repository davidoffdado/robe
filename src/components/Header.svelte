<script>
  import ActiveDays from "./ActiveDays.svelte";
</script>

<nav class="header">
  <div class="inner">
    <h1 class="logo">robe.</h1>
    <ul class="nav">
      <li><a href="#/">Home</a></li>
      <li><a href="#/about">About</a></li>
      <li><a href="#/contact">Contact</a></li>
    </ul>
    <ActiveDays />
  </div>
</nav>

<style>
  .header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background: #fff;
    border-bottom: 1px solid #eee;
    z-index: 1000;
    display: flex;
    justify-content: center;
  }

  .inner {
    width: 100%;
    max-width: 1400px;
    margin: 0 auto;
    padding: 1rem clamp(1rem, 5vw, 3rem);
    display: grid;
    grid-template-columns: 1fr auto 1fr;
    align-items: center;
    box-sizing: border-box;
  }

  .logo {
    font-weight: 800;
    font-size: 1.25rem;
    color: #ff4f70;
    justify-self: start;
  }

  .nav {
    list-style: none;
    display: flex;
    gap: 1.5rem;
    margin: 0;
    padding: 0;
    justify-self: center;
  }

  .nav a {
    text-decoration: none;
    color: #111;
    font-weight: 600;
  }

  :global(.inner > :last-child) {
    justify-self: end;
  }

@media (max-width: 640px) {
  .inner {
    display: flex;              /* invece di grid */
    flex-direction: column;     /* in colonna */
    align-items: center;        /* centrati orizzontalmente */
    text-align: center;
    gap: 0.75rem;
  }

  .nav {
    flex-wrap: wrap;
    justify-content: center;
  }
  
  
}

  

</style>
