<script>
  export let index;
  export let title;
    export let subtitle;   // sottotitolo al posto della descrizione
  export let image;
  export let date;
    export let link; // nuovo: URL della pagina o risorsa da aprire


  // Palette di colori vivaci (sequenza per evitare doppioni vicini)
  const colors = [
    "#FF6B6B", // rosso
    "#FFD93D", // giallo
    "#6BCB77", // verde
    "#4D96FF", // blu
    "#FF6EC7", // rosa
    "#FF914D", // arancio
    "#845EC2", // viola
    "#00C9A7", // turchese
    "#FFC75F", // oro
    "#F9F871", // lime
    "#FF9671", // corallo
    "#008F7A"  // verde petrolio
  ];

  let bgColor = colors[index % colors.length];
</script>



<a class="card" href={link}>
  <div class="top-bar">
    <span class="tag">#{index}</span>
    <span class="date">{date}</span>
  </div>

  <div class="image-wrapper" style="background-color: {bgColor};">
    <img src={image} alt={title} />
  </div>

  <h2 class="title" style="--highlight:{bgColor};">{title}</h2>
    {#if subtitle}
    <h3 class="subtitle">{subtitle}</h3>
  {/if}
</a>

<style>
  .card {
    background: #fff;
    padding: 1.2rem;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    transition: transform 0.2s, border 0.2s;
    border: 1px solid transparent; /* di base invisibile */
  }

  .card:hover {
    transform: translateY(-4px);       /* piccolo spostamento */
    border: 1px solid #000;            /* bordo nero netto */
  }

  .top-bar {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
  }

  .tag {
    background: #000;
    color: #fff;
    font-weight: bold;
    font-size: 0.9rem;
    padding: 0.3rem 0.7rem;
  }

  .date {
  background: #fff;   /* sfondo bianco */
  color: #000;        /* testo nero */
  border: 1px solid #000; /* opzionale: bordo per darle risalto */
  font-weight: 600;
  font-size: 0.85rem;
  padding: 0.3rem 0.7rem;
  }

  .image-wrapper {
    width: 100%;
    padding: 1rem;
    margin-bottom: 1rem;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .image-wrapper img {
    width: 100%;
  }

  h2 {
    margin: 0.5rem 0;
    font-size: 1.4rem;
    font-weight: 800;
    font-family: 'Inter', sans-serif;
    color: #000;
  }

  p {
    font-size: 0.95rem;
    line-height: 1.5;
    color: #444;
  }
  
 .title {
    position: relative;
    margin: 0.5rem 0 0.25rem;
    font-size: 1.5rem;
    font-weight: 800;
    line-height: 1.2;
    color: #000;
    font-family: "Poppins", sans-serif;
    text-align: left;
    display: inline-block; /* così il background si adatta al testo */
  }

  /* Evidenziazione in hover */
  .title::before {
    content: "";
    position: absolute;
    left: 0;
    bottom: 0.15em;
    width: 100%;
    height: 0.5em;
    background: var(--highlight);
    z-index: -1;
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s ease;
  }

  .card:hover .title::before {
    transform: scaleX(1); /* si anima l’evidenziatore */
  }

  .subtitle {
    margin: 0;
    font-size: 1rem;
    font-weight: 500;
    color: #555;
    line-height: 1.4;
    text-align: left;
    font-family: "Poppins", sans-serif;
  }

  
 
</style>
