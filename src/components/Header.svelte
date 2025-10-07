
<nav class="header">
  <div class="inner">
    <h1 class="logo">robe</h1>
    <ul class="nav">
      <li><a href="#/">Home</a></li>
      <li><a href="#/about">About</a></li>
      <li><a href="#/contact">Contact</a></li>
    </ul>
  </div>
</nav>

<style>
  /* L’intero header si estende al 100% */
  .header {
    width: 100%;
    background: #fff;        /* colore intero header */
    border-bottom: 1px solid #eee;
  }

  /* Contenuto centrato */
  .inner {
    max-width: 70rem;        /* limite centrale su desktop */
    margin: 0 auto;
    padding: 1rem 5vw;       /* padding relativo */
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .logo {
    font-weight: 800;
    font-size: 1.25rem;
	color: #ff4f70;
  }

  .nav {
    list-style: none;
    display: flex;
    gap: 1.5rem;
    margin: 0;
    padding: 0;
  }
  .nav a {
    text-decoration: none;
    color: #111;
    font-weight: 600;
  }

  /* Mobile: tutto centrato */
  @media (max-width: 640px) {
    .inner {
      flex-direction: column;
      text-align: center;
      gap: 0.75rem;
    }
    .nav {
      flex-wrap: wrap;
      justify-content: center;
    }
  }
  
</style>
