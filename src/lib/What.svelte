<script>
  import Project from "./Project.svelte";
  import FaChevronRight from "svelte-icons/fa/FaChevronRight.svelte";
  import FaChevronLeft from "svelte-icons/fa/FaChevronLeft.svelte";
  import { fly } from "svelte/transition";

  let planpals = {
    preview: "images/planpals-1.gif",
    title: "PlanPals",
    description:
      "Plan your next event without worrying about the frustrations that come with planning events.",
    github: "https://github.com/cptleo92/PlanPals",
    live: "https://www.plan-pals.com/",
    tools: ["React", "Express", "MaterialUI", "MongoDB", "Jest"],
  };

  let meetgreet = {
    preview: "images/meetgreet-preview-1.gif",
    title: "MeetGreet",
    description:
      "Full stack clone of Meetup, a social platform for users to find groups, coordinate in-person events, and find true value in the friends we made along the way.",
    github: "https://github.com/cptleo92/MeetGreet",
    live: "https://meetgreet-lc.herokuapp.com/",
    tools: ["React", "Redux", "Ruby on Rails", "Typescript", "PostgreSQL"],
  };

  let jsbilliards = {
    preview: "images/pool-demo.gif",
    title: "JS Billiards",
    description:
      "A fully functional, smooth and intuitive billiards game for the browser.",
    github: "https://github.com/cptleo92/jsbilliards",
    live: "https://cptleo92.github.io/JSBilliards/",
    tools: ["HTML Canvas", "Javascript"],
  };

  let stickcontrol = {
    preview: "images/stickcontrol.gif",
    title: "Interactive Stick Control",
    description:
      "Stick Control for the Snare Drummer. A visual practice guide with metronome.",
    github: "https://github.com/cptleo92/StickControl",
    live: "https://stick-control.netlify.app/",
    tools: ["Svelte", "Tailwind", "Netlify", "Vexflow"],
  }

  let projects = [planpals, meetgreet, stickcontrol, jsbilliards];
  let current = 0;
  let direction;

  const handleClick = (dir) => {
    direction = dir;
    if (dir === "left") {
      current = (current - 1 + projects.length) % projects.length;
    } else {
      current = (current + 1) % projects.length;
    }
  };

  const getX = () => {
    if (direction === "left") {
      return 500;
    } else {
      return -500;
    }
  };
</script>

<section>
  <img id="Work" class="heading" src="images/what.svg" alt="what have i done" />

  <div class="container-container">
    {#each [projects[current]] as project (current)}
      <div
        in:fly={{
          x: getX(),
          duration: 500,
          delay: 500,
        }}
        out:fly={{ x: getX() * -1, duration: 500 }}
        class="projects-container"
      >
        <Project {project} />
      </div>
    {/each}

    <div class="icon icon-left" on:click={() => handleClick("left")}>
      <FaChevronLeft />
    </div>
    <div class="icon icon-right" on:click={() => handleClick("right")}>
      <FaChevronRight />
    </div>
  </div>
</section>

<style>
  section {
    height: 120vh;
  }

  .container-container {
    position: relative;
  }

  .heading {
    padding-top: 6rem;
    width: 90%;
    margin: 4rem 0;
  }

  .icon {
    position: absolute;
    width: 30px;
    color: #e5e5e5;
    cursor: pointer;
    top: 130px;
  }

  .icon-left {
    left: -33px;
  }

  .icon-right {
    right: -33px;
  }

  .icon:hover {
    scale: 110%;
    transition: scale 0.2s ease-out;
  }

  .icon:active {
    scale: 80%;
  }

  .projects-container {
    position: absolute;
  }

  @media (min-width: 480px) {
    .icon {
      top: 230px;
    }
  }

  @media (min-width: 960px) {
    .icon {
      top: 335px;
    }

    .container-container {
      width: 600px;
      margin: auto;
    }
  }
</style>
