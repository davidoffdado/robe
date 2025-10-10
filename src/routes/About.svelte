<section class="about">
<h1> ABOUT </h1>
  <details>
    <summary><h2>What</h2></summary>
    <p>
      Il progetto ospita idee di <b>data journalism</b>, trasformandole in storie interattive e visuali,
      con l’obiettivo di smontare la retorica della noia dietro i numeri e di fornire un'informazione più coinvolgente.
    </p>
  </details>
 
  <details>
    <summary><h2>Why</h2></summary>
    <p>
      Dietro <b>robe</b> c'è prima di tutto la voglia di fare qualcosa, di creare questo spazio, di sporcarsi le mani con la ricerca di informazioni,
      l'analisi dei dati e lo sviluppo web. <br>
      Rimosso il primo strato del "fare qualcosa perché si vuole fare", l'idea alla base è <b>rallentare</b>, costruire un'alternativa al giornalismo veloce,
      alle newsletter giornaliere, alle notizie dell'ultima ora. Qui si respira, aspettando un mese o più per la pubblicazione di un nuovo contenuto. <br>
      Infine, è necessario fare i conti con l'attuale soglia dell'attenzione a livello mondiale. Essendo circondati da stimoli in ogni secondo della nostra vita,
      facciamo sempre più fatica a dedicare del tempo alla lettura, all'ascolto o alla visione di qualcosa. Attraverso l'interazione e gli aspetti visivi,
      cerchiamo di <b>intrattenere e informare</b>.
    </p>
  </details>
  <details>
    <summary><h2>Who</h2></summary>
    <div class="team">
      
      <!-- Autore 1 -->
      <div class="member">
        <button class="author-btn" on:click={() => document.getElementById('david-dialog').showModal()}>
          <img src="./new.jpg" alt="David Ruffini" />
          <h3>David Ruffini</h3>
        </button>
      </div>

      <!-- Autore 2 (replica per esempio) 
      <div class="member">
        <button class="author-btn" on:click={() => document.getElementById('maria-dialog').showModal()}>
          <img src="./new.jpg" alt="Maria Rossi" />
          <h3>Maria Rossi</h3>
        </button>
      </div>  -->

	  
    </div>
  </details>
  
  <!-- Dialog overview David -->
<dialog id="david-dialog" class="author-dialog">
  <div class="dialog-content">
    <img src="./new.jpg" alt="David Ruffini" />
    <h3>David Ruffini</h3>
    <p>
      Statistico e data journalist, ha collaborato con <b>Il Sole 24 Ore</b>, <b>Wired Italia</b> e <b>Aliseo Editoriale</b>.  
      Scrive di probabilità nella newsletter <a href="https://aalea.substack.com/" target="_blank">àlea</a>.  
      Tutti i suoi lavori sono nel <a href="https://www.davidruffini.com/" target="_blank">sito personale</a>.
    </p>
    <button class="close-btn" on:click={() => document.getElementById('david-dialog').close()}>Chiudi</button>
  </div>
</dialog>

<!-- Dialog overview Maria
<dialog id="maria-dialog" class="author-dialog">
  <div class="dialog-content">
    <img src="./new.jpg" alt="Maria Rossi" />
    <h3>Maria Rossi</h3>
    <p>
      Giornalista e designer di dati, appassionata di visualizzazione interattiva.  
      Collabora con testate indipendenti e progetti culturali, sviluppando storie digitali con forte impatto visivo.
    </p>
    <button class="close-btn" on:click={() => document.getElementById('maria-dialog').close()}>Chiudi</button>
  </div>
</dialog>  -->
  
</section>

<style>
.about {
  max-width: 700px;
  margin: 3rem auto;
  text-align: left;
  line-height: 1.6;
  padding: 0 1rem;
}

.about p {
  font-size: 1.1rem;
  color: #333;
  margin-top: 0.75rem;
}

/* Evidenziazione dinamica */
.about b {
  position: relative;
  font-weight: 800;
  display: inline-block; /* evita spezzatura */
  z-index: 1;
}
.about b::before {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 0.6em;
  background: linear-gradient(90deg, #fff06b, #ffe15a);
  z-index: -1;
  transform: scaleX(0);
  transform-origin: left;
}
details[open] b::before {
  animation: highlight 0.8s ease forwards;
}
@keyframes highlight {
  to { transform: scaleX(1); }
}

/* Contenitori */
details {
  margin-bottom: 1.5rem;
  border-bottom: 1px solid #eee;
  padding-bottom: 1rem;
}
summary {
  display: flex;
  justify-content: space-between; /* titolo a sx, icona a dx */
  align-items: center;
  cursor: pointer;
  list-style: none;
  width: 100%;
  padding: 0; /* niente padding extra */
  box-sizing: border-box;
}

summary::-webkit-details-marker {
  display: none;
}

/* Titolo dentro summary */
summary h2 {
  margin: 0;
  font-size: 2rem;
  font-weight: 800;
  text-align: left;
  flex: 1; /* prende tutto lo spazio a sinistra */
}

/* Icona custom (+ / -) con più spazio dal testo */
summary::after {
  content: "+";
  font-size: 1.5rem;
  flex: 0 0 3rem;     /* colonna fissa più larga (prima era 2rem) */
  text-align: right;  /* icona allineata a destra nella colonna */
  margin-left: 30rem;  /* spazio extra tra testo e icona */
}
details[open] summary::after {
  content: "−";
}


/* Sezione Team */
.team {
  display: flex;
  gap: 1.5rem;
  margin-top: 1rem;
}

.member a {
  display: flex;
  align-items: center;
  gap: 1rem;
  text-decoration: none;
  color: inherit;
}

.member img {
  width: 150px;
  height: 150px;
  border-radius: 0;
  object-fit: cover;
  flex-shrink: 0;
}

.member h3 {
  margin: 0;
  font-size: 1.1rem;
  font-weight: 700;
}


.info a {
  display: inline;
  color: inherit;                 /* eredita il colore del testo */
  text-decoration: none;          /* tolgo la sottolineatura standard */
  border-bottom: 2px solid #000;  /* sottolineatura personalizzata */
  font-weight: 600;
  padding-bottom: 0.05em;         /* piccolo spazio tra testo e underline */
  transition: background 0.25s, color 0.25s;
}

.info a:hover {
  background: #000;   /* sfondo nero */
  color: #fff;        /* testo bianco sopra lo sfondo */
}

.open-dialog {
  background: none;
  border: none;
  padding: 0;
  cursor: pointer;
  text-align: center;
}

/* Dialog */
/* Dialog sempre bianco */
.author-dialog {
  border: none;
  border-radius: 8px;
  padding: 0;
  max-width: 500px;
  width: 90%;
  background: #fff;
  color: #111;
}

/* Elimina effetto nero scuro del backdrop */
.author-dialog::backdrop {
    background: rgba(255, 255, 255, 0.2); /* leggero velo bianco trasparente */
  backdrop-filter: blur(8px);           /* sfocatura */
  -webkit-backdrop-filter: blur(8px);   /* compatibilità Safari */
}

/* Se vuoi nessun overlay */
.author-dialog::backdrop {
  background: transparent;
}


.dialog-content {
  padding: 2rem;
  text-align: center;
}

.dialog-content img {
  width: 300px;
  height: 300px;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: 1rem;
}

.dialog-content h3 {
  font-size: 1.5rem;
  font-weight: 800;
  margin-bottom: 1rem;
}

.dialog-content p {
  font-size: 1rem;
  color: #333;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.dialog-content a {
  color: inherit;
  border-bottom: 2px solid #000;
  text-decoration: none;
  font-weight: 600;
}
.dialog-content a:hover {
  background: #000;
  color: #fff;
}

.close-btn {
  background: #111;
  color: #fff;
  border: none;
  padding: 0.6rem 1.2rem;
  border-radius: 6px;
  cursor: pointer;
  font-weight: 600;
}
.close-btn:hover {
  background: #ff4f70;
}

.author-btn {
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
  text-align: center;
}

.member h3 {
  margin-top: 0.5rem;
  font-size: 1rem;
  font-weight: 600;
  color: #111;
}

@media (max-width: 640px) {
summary h2 {
  margin: 0;
  font-size: 2rem;
  font-weight: 800;
  text-align: left;
}


.member {
    flex-direction: column;   /* foto e testo uno sotto l'altro */
    align-items: flex-start;  /* allineati a sinistra */
    text-align: left;
    gap: 0.5rem;
  }

  .member img {
    width: 70px;
    height: 70px;
  }

  .info {
    width: 100%;              /* la descrizione prende tutta la riga */
  }

  .info h3 {
    margin-top: 0.5rem;
    font-size: 1.1rem;
  }

  .info p {
    font-size: 0.95rem;
  }
  
    summary {
    display: flex;
    justify-content: space-between; /* titolo a sx, icona a dx */
    width: 100%;
  }

  summary::after {
    margin-left: 0; /* elimina spazio extra */
  }
  
.team {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
  }
  .member img {
    width: 120px;
    height: 120px;
  }
  .dialog-content {
    padding: 1.5rem;
  }
  .dialog-content img {
    width: 200px;
    height: 200px;
  }

}
</style>
