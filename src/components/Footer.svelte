<footer class="footer">
  <div class="footer-inner">
    <!-- Social -->
    <div class="social">
      <a href="https://instagram.com" target="_blank" aria-label="Instagram">
        <i class="fab fa-instagram"></i>
      </a>
      <a href="https://twitter.com" target="_blank" aria-label="Twitter">
        <i class="fab fa-twitter"></i>
      </a>
      <a href="https://www.linkedin.com/" target="_blank" aria-label="LinkedIn">
        <i class="fab fa-linkedin"></i>
      </a>
    </div>

    <!-- Copyright -->
    <p class="copy">© 2025 robe</p>

    <!-- Link interni -->
    <div class="links">
      <a href="#/about">ABOUT</a>
      <a href="#/contact">CONTATTI</a>
    </div>
  </div>
</footer>

<style>
  .footer {
    margin-top: 2rem;
    padding: 1rem 2rem;
  }

  .footer-inner {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  /* Social */
  .social {
    display: flex;
    gap: 1rem;
  }

  .social a {
    color: #111;
    font-size: 1.2rem;
    transition: color 0.2s ease;
  }

  .social a:hover {
    color: #ff4f70;
  }

  /* Copyright */
  .copy {
    margin: 0;
    font-weight: 600;
    font-size: 0.95rem;
  }

  /* Link interni */
  .links {
    display: flex;
    gap: 1.5rem;
  }

  .links a {
    color: #111;
    font-weight: 600;
    text-decoration: none;
    transition: color 0.2s ease;
  }

  .links a:hover {
    text-decoration: underline;
    color: #ff4f70;
  }
  

  /* --- Mobile layout --- */
  @media (max-width: 640px) {
    .footer-inner {
      flex-direction: column;
      gap: 1rem;
      text-align: center;
    }
	
	.links {
      order: 1; /* prima */
      justify-content: center;
    }

    .copy {
      order: 2; /* poi */
    }

    .social {
      order: 3; /* in fondo */
      justify-content: center;
    }
  }
</style>
