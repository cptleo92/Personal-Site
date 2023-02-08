<script>
  import { fade, fly } from "svelte/transition";
  import { onMount } from "svelte";
  import { cubicOut } from "svelte/easing";

  let clicks = 0;

  const handleClick = () => {
    if (clicks < 10) clicks++;
  };

  let options = {
    threshold: 0.5,
  };

  let transition = false;

  onMount(() => {
    let observer = new IntersectionObserver((entries, observer) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          transition = true;
          observer.unobserve(entry.target);
        }
      });
    }, options);

    let section = document.querySelector(".who");
    observer.observe(section);
  });
</script>

<section class="who">
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div id="Me" class="container" on:click={handleClick}>
    <img class="heading" src="images/who.svg" alt="who am i" />

    {#if clicks < 10}
      <div out:fly={{ x: 500, duration: 1000 }}>
        {#if clicks >= 1}
          <h4 transition:fade>2</h4>
        {/if}
        {#if clicks >= 2}
          <h4 transition:fade>4</h4>
        {/if}
        {#if clicks >= 3}
          <h4 transition:fade>6</h4>
        {/if}
        {#if clicks >= 4}
          <h4 transition:fade>0</h4>
        {/if}
        {#if clicks >= 5}
          <h4 transition:fade>1!</h4>
        {/if}
        {#if clicks >= 6}
          <h4 transition:fade>!</h4>
        {/if}
        {#if clicks >= 7}
          <h4 transition:fade>!</h4>
        {/if}
        {#if clicks >= 8}
          <h4 transition:fade>!</h4>
        {/if}
        {#if clicks >= 9}
          <h4 transition:fade>!</h4>
        {/if}
      </div>
    {/if}
  </div>

  <!-- <img
    on:click={handleImgClick}
    style={`transform: rotateY(${clicked ? "180deg" : 0});`}
    class="avatar"
    src="images/avatar.jpg"
    alt="avatar"
  /> -->

  <figure>
    <a
      href="https://www.instagram.com/tattoosintransit/"
      target="_blank"
      rel="noreferrer"
    >
      <img
        src="images/Sad_Man_Leo-removebg.png"
        alt="an accurate portrayal"
        class="avatar"
      />
    </a>
    <figcaption><em>Designed by @tattoosintransit</em></figcaption>
  </figure>

  <div class="text">
    <p
      class="slide slide-1"
      style={transition && "opacity: 1; transform: translateX(0);"}
    >
      I’m Leo, a software engineer with a focus on web development. I enjoy
      turning ideas into applications, working front to back to create engaging,
      responsive, and ultimately impactful digital experiences.
    </p>

    <p
      class="slide slide-2"
      style={transition && "opacity: 1; transform: translateX(0);"}
    >
      I'm fascinated by how vastly creative the world of programming is, and the
      brilliant minds who leverage these tools and technologies to build new and
      exciting experiences for users and fellow hackers. My dream is to explore
      as much of this world as I can and leave an impression of my own one day.
    </p>
    <p
      class="slide slide-3"
      style={transition && "opacity: 1; transform: translateX(0);"}
    >
      Outside of computers, my hobbies include recreational volleyball, fantasy
      fiction, metal concerts, and implementing depth-first algorithms on
      inverted trees (a.k.a. rock climbing). My latest hobby is drumming. Reach
      out if you want to start a band!
    </p>
  </div>
</section>

<style>
  section {
    height: 120vh;
  }

  .container {
    padding-top: 6rem;
    display: block;
    width: 95%;
    cursor: pointer;
    height: 4rem;
  }

  .heading {
    width: 90%;
  }

  .heading:hover {
    scale: 102%;
    transition: scale 0.2s ease-in-out;
  }

  figure {
    width: 100%;
    margin: 1rem 0;
    text-align: center;
  }

  .avatar {
    width: 168px;
    height: 168px;
    box-shadow: 1px 1px 8px #000000;
    border: 3px solid white;
    border-radius: 100%;
    cursor: pointer;
    transition: all 0.5s ease-in;
    object-fit: cover;
    object-position: 0 0;
  }

  figcaption {
    text-align: center;
    margin: 1rem 0 2rem 0;
    font-size: 0.8em;
  }

  .avatar:hover {
    scale: 105%;
    transition: scale 0.3s ease-in-out;
  }

  .text {
    display: flex;
    flex-direction: column;
  }

  p {
    opacity: 0;
    margin-bottom: 2rem;
  }

  div {
    display: flex;
    height: 1rem;
  }

  .slide-1 {
    transform: translateX(-30%);
    transition: all 300ms ease-out;
  }

  .slide-2 {
    transform: translateX(30%);
    transition: all 300ms ease-out 200ms;
  }

  .slide-3 {
    transform: translateX(-30%);
    transition: all 300ms ease-out 400ms;
  }

  /* .sad {
    display: block;
    margin: 2rem auto;
    width: 30vh;
    height: 30vh;
    border: 3px solid white;
    border-radius: 100%;
    object-fit: cover;
    object-position: 0 0;
  } */

  @media (min-width: 480px) {
    .avatar {
      width: 200px;
      height: 200px;
    }
  }

  @media (min-width: 960px) {
    .avatar {
      width: 300px;
      height: 300px;
    }

    .container {
      padding-bottom: 3rem;
    }
  }
</style>
