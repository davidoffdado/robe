<section class="about">
<h1> ABOUT </h1>
  <details>
    <summary><h2>Cos'è?</h2></summary>
    <p>
      Il progetto ospita idee di <b>data journalism</b>, trasformandole in storie interattive e visuali,
      con l’obiettivo di smontare la retorica della noia dietro i numeri e di fornire un'informazione più coinvolgente.
    </p>
  </details>
 
  <details>
    <summary><h2>Perché?</h2></summary>
    <p>
      Dietro <b>robe</b> c'è prima di tutto la voglia di fare qualcosa, di creare questo spazio, di sporcarsi le mani con la ricerca di informazioni,
      l'analisi dei dati e il design del risultato finale. <br>
      Rimosso il primo strato del "fare qualcosa perché si vuole fare", l'idea alla base è <b>rallentare</b>, costruire un'alternativa al giornalismo veloce,
      alle newsletter giornaliere, alle notizie dell'ultima ora. Qui si respira, aspettando un mese o più per la pubblicazione di un nuovo contenuto. <br>
      Infine, è necessario fare i conti con l'attuale soglia dell'attenzione a livello mondiale. Essendo circondati da stimoli in ogni secondo della nostra vita,
      facciamo sempre più fatica a dedicare del tempo alla lettura, all'ascolto o alla visione di qualcosa. Attraverso l'interazione e gli aspetti visuali,
      vogliamo che i nostri prodotti siano in grado di <b>intrattenere e informare</b>.
    </p>
  </details>
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
  margin-right:40rem
}

/* Icona custom (+ / -) */
summary::after {
  content: "+";
  font-size: 1.5rem;
}
details[open] summary::after {
  content: "−";
}

@media (max-width: 640px) {
summary h2 {
  margin: 0;
  font-size: 2rem;
  font-weight: 800;
  text-align: left;
}

}
</style>
