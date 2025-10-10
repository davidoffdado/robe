<script>
  import ProjectCard from "../components/ProjectCard.svelte";
  import sample from "../assets/sample.png";
  import { tweened } from "svelte/motion";
  import { cubicOut } from "svelte/easing";

  let projects = [
    { title: "Analisi elezioni 2025", subtitle: "Un progetto interattivo sui dati elettorali", image: sample, date: "Gen 2025", link: "https://davidoffdado.github.io/pizza/"}
  ];
  
    let projectsOrdered = [...projects].reverse();

  // numero totale di progetti
  const total = projects.length;

  // animazione da 0 a total
  let count = tweened(0, { duration: 1500, easing: cubicOut });
  count.set(total); // triggera animazione
</script>

<section class="counter">
  <h2>
    Finora abbiamo pubblicato 
    <span class="number">{Math.round($count)}</span> progetto
  </h2>
</section>

<section class="projects">
  {#each projectsOrdered as project, i}
      <ProjectCard index={projects.length - i} {...project} />
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
  
  .counter {
    text-align: center;
    margin: 2rem 0;
  }

  .counter h2 {
    font-size: 1.5rem;
    font-weight: 700;
    color: #111;
  }

  .counter .number {
    font-size: 2rem;
    font-weight: 800;
    color: #ff4f70; /* colore vivace per risaltare */
    display: inline-block;
    margin: 0 0.25rem;
    transition: transform 0.3s ease;
  }

  .counter .number:hover {
    transform: scale(1.2); /* effetto pop al passaggio */
  }
  
  @media (max-width: 640px) {
  .projects {
    margin-top: 4rem; /* aumenta la distanza su mobile */
  }
}


</style>
