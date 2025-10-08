<script>
  import ProjectCard from "../components/ProjectCard.svelte";
  import sample from "../assets/sample.png";

  let projects = [
    { title: "Analisi elezioni 2025", subtitle: "Un progetto interattivo sui dati elettorali", image: sample, date: "Gen 2025" },
    { title: "Clima e città", subtitle: "Come le città stanno cambiando con il clima", image: sample, date: "Dic 2024" },
    { title: "Musica e dati", subtitle: "Visualizzazioni divertenti sui trend musicali", image: sample, date: "Nov 2024" },
    { title: "Cinema e numeri", subtitle: "Analisi dei dati al botteghino", image: sample, date: "Ott 2024" },
    { title: "Sport e statistiche", subtitle: "Numeri curiosi sul calcio", image: sample, date: "Set 2024" }
  ];
</script>

<section class="projects">
  {#each projects as project, i}
    <ProjectCard index={i + 1} {...project} />
  {/each}
</section>

<style>

  .projects {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 2rem;
    justify-content: center; /* la griglia è sempre centrata */
	margin-top: 0rem;
  }
  
  @media (max-width: 640px) {
  .projects {
    margin-top: 4rem; /* aumenta la distanza su mobile */
  }
}


</style>
