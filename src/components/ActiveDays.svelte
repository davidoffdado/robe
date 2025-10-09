<script>
  import { onMount } from "svelte";

  const startDate = new Date("2024-10-01");

  let currentDate = new Date();
  let totalDays = Math.floor((currentDate - startDate) / (1000 * 60 * 60 * 24)) + 1;
  let displayDays = 1;

  function animateCounter() {
    let step = Math.ceil(totalDays / 50);
    const interval = setInterval(() => {
      displayDays += step;
      if (displayDays >= totalDays) {
        displayDays = totalDays;
        clearInterval(interval);
      }
    }, 40);
  }

  onMount(animateCounter);
</script>

<div class="active-days">
  <span class="label">online da</span>
  <span class="number">{displayDays}</span>
  <span class="label">giorni</span>
</div>

<style>
  .active-days {
    display: flex;
    align-items: baseline;
    gap: 0.3rem;
    font-family: 'Poppins', sans-serif;
    font-size: 0.95rem;
    font-weight: 600;
    color: #333;
  }

  .number {
    font-size: 1.1rem;
    font-weight: 900;
    color: #000;
  }
  
  

</style>
