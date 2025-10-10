<section class="contact">
  <h1>CONTACTS</h1>
  <p>
    Vuoi collaborare, proporre un'idea o commissionare un lavoro? Puoi scriverci una mail, per qualsiasi cosa!
  </p>

  <!-- Dettaglio "Collabora" -->
  <details>
    <summary><h2>Collaborazioni</h2></summary>
    <p>
      Siamo sempre aperti a <b>nuove idee</b>, collaborazioni e progetti condivisi.  
      Se vuoi proporre un articolo, un'idea su dati da analizzare o un progetto interattivo, scrivici:  
      raccontaci la tua proposta e valuteremo insieme come realizzarla.
    </p>
  </details>
  
  <!-- Dettaglio "Lavoriamo a qualcosa" -->
  <details>
    <summary><h2>Commissioni</h2></summary>
    <p>
    Vuoi raccontare <b>i tuoi dati</b> in modo originale e interattivo?  
    Realizziamo progetti di data journalism, visualizzazioni e storie su misura  
    per aziende, enti e redazioni.
    </p>
  </details>
  
  <!-- Dettaglio "Errori" -->
  <details>
    <summary><h2>Errori</h2></summary>
    <p>
    Possiamo sbagliare. Se ti accorgi di un nostro errore, non esitare a farcelo notare: significa che chi ci legge è attento!
    </p>
  </details>

  <ul class="contact-list">
    <li>
      <a href="mailto:tuoemail@example.com" class="highlight-mail">
        <i class="fas fa-envelope"></i> tuoemail@example.com
      </a>
    </li>
  </ul>
</section>

<style>
  .contact {
    max-width: 600px;
    margin: 3rem auto;
    line-height: 1.6;
    text-align: left;
    padding: 0 1rem;
  }

  .contact h1 {
    font-size: 2.2rem;
    font-weight: 800;
    margin-bottom: 1rem;
  }

  .contact p {
    font-size: 1.1rem;
    color: #333;
    margin-bottom: 1.5rem;
  }

  /* Dettaglio collabora */
  details {
    margin-bottom: 1.5rem;
    border-bottom: 1px solid #eee;
    padding-bottom: 1rem;
  }

  summary {
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
    list-style: none;
  }

  summary::-webkit-details-marker {
    display: none;
  }

  summary h2 {
    margin: 0;
    font-size: 1.5rem;
    font-weight: 700;
  }

  summary::after {
    content: "+";
    font-size: 1.5rem;
  }
  details[open] summary::after {
    content: "−";
  }

  /* Lista contatti */
  .contact-list {
    list-style: none;
    padding: 0;
    margin-top: 2rem;
    font-size: 1.1rem;
  }

  .contact-list a {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
  }

  .contact-list i {
    font-size: 1.2rem;
    color: #111;
    transition: transform 0.3s ease, color 0.3s ease;
  }

  /* Mail con pennellata */
  .highlight-mail {
    position: relative;
    font-weight: 700;
    text-decoration: none;
    color: #111;
    z-index: 1;
    transition: color 0.3s ease;
  }

  .highlight-mail::before {
    content: "";
    position: absolute;
    left: 0;
    bottom: 0.1em;
    width: 100%;
    height: 0.6em;
    background: linear-gradient(90deg, #fff06b, #ffe15a);
    z-index: -1;
    transform: scaleX(1);
    transform-origin: left;
    transition: background 0.3s ease;
  }

  .highlight-mail:hover {
    color: #ff4f70;
  }

  .highlight-mail:hover::before {
    background: linear-gradient(90deg, #ffb3c0, #ff4f70);
  }

  .highlight-mail:hover i {
    transform: rotate(-10deg) scale(1.2);
    color: #ff4f70;
  }

  @media (max-width: 640px) {
    .contact {
      padding: 0 1rem;
    }

    .contact-list {
      font-size: 1rem;
    }
  }
</style>
