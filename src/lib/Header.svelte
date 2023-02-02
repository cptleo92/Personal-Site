<script>
  import { fly } from "svelte/transition";

  let hideHeader = true;

  let y = 0;
  let lastY = 0;
  let offset = 0;

  $: updateClass(y);

  const updateClass = (y) => {
    const dy = lastY - y;
    lastY = y;

    if (y < offset) {
      hideHeader = false;
    } else if (dy < 0) {
      hideHeader = true;
    } else {
      hideHeader = false;
    }
  };

  const scrollIntoView = (e) => {
    const target = e.target.textContent;
    const el = document.querySelector(`#${target}`);

    if (!el) return;
    el.scrollIntoView({
      behavior: "smooth",
    });
  };
</script>

<svelte:window bind:scrollY={y} />

{#if !hideHeader}
  <header class="container" transition:fly={{ y: -50, duration: 400 }}>
    <button on:click={scrollIntoView} class="header-btn"> Who </button>
    <button on:click={scrollIntoView} class="header-btn mid"> What </button>
    <button on:click={scrollIntoView} class="header-btn"> Where </button>
  </header>
{/if}

<style>
  .container {
    position: fixed;
    width: 100%;
    height: 50px;
    top: 0;
    display: flex;
    justify-content: center;
    margin: 1rem auto;
    z-index: 10;
  }

  .header-btn {
    width: 90px;
    height: 40px;
    background: #cfc7bf;
    border-radius: 10px;
    font-weight: 500;
    font-size: 1rem;
    font-family: Roboto;
    cursor: pointer;
  }

  .header-btn:hover {
    scale: 105%;
    transition: scale 0.2s ease-out;
  }

  .mid {
    margin: 0 20px;
  }
</style>
