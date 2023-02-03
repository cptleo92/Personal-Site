<script>
  import { fly } from "svelte/transition";

  let hideHeader = false;

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
    <button on:click={scrollIntoView} class="header-btn"> What </button>
    <button on:click={scrollIntoView} class="header-btn "> Where </button>
    <button class="header-btn resume"
      ><a href="Leo_Cheng_SE_Resume.pdf">Resume</a></button
    >
  </header>
{/if}

<style>
  .container {
    position: fixed;
    width: 100%;
    height: 50px;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    margin: auto;
    padding: 1rem 0;
    margin-top: 0;
    z-index: 10;
    backdrop-filter: blur(2px);
  }

  .header-btn {
    width: 75px;
    height: 40px;
    background: #e4e4e4;
    border-radius: 6px;
    font-weight: 500;
    font-size: 0.9rem;
    font-family: Roboto;
    cursor: pointer;
  }

  .resume {
    background: transparent;
    color: white;
    border: 2px solid white;
  }

  .header-btn:not(:first-child) {
    margin-left: 0.5rem;
  }

  .header-btn:hover {
    scale: 105%;
    transition: scale 0.2s ease-out;
  }

  @media (min-width: 480px) {
    .header-btn {
      width: 90px;
      font-size: 1rem;
    }
  }

  @media (min-width: 960px) {
    .container {
      justify-content: right;
    }

    .header-btn {
      margin-right: 1.5rem;
      width: 120px;
      font-size: 1.2rem;
    }
  }
</style>
