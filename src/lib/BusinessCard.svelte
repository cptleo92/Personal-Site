<script>
  import { fly } from "svelte/transition";
  let showCard = false;

  const handleClick = () => {
    showCard = true;
  };
</script>

{#if !showCard}
  <button in:fly={{ delay: 3500 }} on:click={handleClick}>Take My Card</button>
{/if}

{#if showCard}
  <div class="card" in:fly={{ y: 50, duration: 1000 }}>
    <img src="images/business.png" alt="business card" />
  </div>
{/if}

<style>
  button {
    display: block;
    margin: 2rem auto;
    min-width: 200px;
    height: 75px;
    background-color: transparent;
    border: 2px solid #ffffff;
    border-radius: 15px;
    color: white;
    font-family: Roboto;
    font-size: 1.5rem;
    text-decoration: underline;
    cursor: pointer;
  }

  button:hover {
    scale: 103%;
    transition: scale 0.2s ease-out;
  }

  .card img {
    display: block;
    margin: 3rem auto;
    width: 90%;
  }
</style>
