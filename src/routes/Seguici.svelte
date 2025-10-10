<section class="contact">
  <h1>FOLLOW US</h1>
  <p>
    Seguici e rimani aggiornato sui nostri progetti:
  </p>

  <ul class="contact-list">
    <li>
      <a href="https://instagram.com/tuoprofilo" target="_blank" aria-label="Instagram">
        <i class="fab fa-instagram"></i> Instagram
      </a>
    </li>
    <li>
      <a href="https://twitter.com/tuoprofilo" target="_blank" aria-label="Twitter">
        <i class="fab fa-twitter"></i> Twitter
      </a>
    </li>
    <li>
      <a href="https://linkedin.com/in/tuoprofilo" target="_blank" aria-label="LinkedIn">
        <i class="fab fa-linkedin"></i> LinkedIn
      </a>
    </li>
  </ul>
</section>

<style>
  .contact {
    max-width: 600px;
    margin: 3rem auto;
    line-height: 1.6;
    padding: 0 1rem;
  }

  .contact h1 {
    font-size: 2.2rem;
    font-weight: 800;
    margin-bottom: 1rem;
    text-align: left;
  }

  .contact p {
    color: #444;
    margin-bottom: 2rem;
    font-size: 1.1rem;
    text-align: left;
  }

  /* Social list di default (desktop): centrata */
  .contact-list {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: center;
    gap: 2rem;
  }

  .contact-list a {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    font-size: 1.2rem;
    font-weight: 600;
    color: #111;
    text-decoration: none;
    transition: transform 0.2s ease, color 0.2s ease;
  }

  .contact-list a:hover {
    color: #ff4f70;
    transform: translateY(-3px);
  }

  .contact-list i {
    font-size: 1.5rem;
    transition: transform 0.2s ease;
  }

  .contact-list a:hover i {
    transform: rotate(10deg) scale(1.2);
    color: #ff4f70;
  }

  /* Mobile: come About, tutto a sinistra */
  @media (max-width: 640px) {
    .contact-list {
      flex-direction: column;     /* verticali invece che in riga */
      align-items: flex-start;    /* allineati a sinistra */
      gap: 1rem;
    }

    .contact-list a {
      font-size: 1.1rem;
    }
  }
</style>
