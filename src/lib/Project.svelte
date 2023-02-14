<script>
  export let project;

  import { DiGithubBadge } from "svelte-icons/di";
  import FaExternalLinkAlt from "svelte-icons/fa/FaExternalLinkAlt.svelte";
</script>

<section>
  <img src={project.preview} alt={`${project.title} preview`} />

  <div class="description">
    <div class="project-text">
      <h3>{project.title}</h3>
      <p>{project.description}</p>
    </div>

    <div class="tools">
      <ul>
        {#each project.tools as tool}
          <li>{tool}</li>
        {/each}
      </ul>
    </div>
  </div>

  <div class="icon-container">
    <a href={project.github} class="icon" target="_blank" rel="noreferrer">
      <DiGithubBadge />
    </a>
    <a href={project.live} class="icon" target="_blank" rel="noreferrer">
      <FaExternalLinkAlt />
    </a>
  </div>
</section>

<style>
  section {
    width: 100%;
    background: rgb(34, 41, 44);
    border-radius: 10px;
  }

  img {
    width: 100%;
    max-height: 200px;
    object-fit: contain;
  }

  p {
    margin: 0.5rem;
  }

  h3 {
    color: #9ab4b9;
    font-weight: 400;
    text-align: center;
  }

  .project-text {
    padding: 0.7rem;
    background-color: #242d30;
  }

  .icon-container {
    display: flex;
    width: 40%;
    margin: auto;
    padding: 2rem 0;
    justify-content: space-between;
  }

  .icon {
    width: 35px;
    height: 35px;
    cursor: pointer;
  }

  .icon:hover {
    opacity: 60%;
    transition: opacity 0.2s ease-in;
  }

  .description {
    display: flex;
    flex-direction: column;
    margin-top: -4px;
  }

  .tools {
    padding: 0.7rem;
    background-color: #334044;
  }

  ul {
    margin: 0.5rem 0;
    display: flex;
    justify-content: center;
  }

  li {
    list-style: none;
    font-size: 0.6rem;
  }

  li:nth-child(odd) {
    color: #c8dee2;
}

  li:not(:first-child) {
    margin-left: 0.7rem;
  }

  @media (min-width: 480px) {
    .tools,
    .project-text {
      padding: 1.2rem;
    }

    li {
      font-size: 0.9rem;
    }
  }

  @media (min-width: 960px) {
    .tools,
    .project-text {
      padding: 1.3rem;
    }

    li {
      font-size: 1.2rem;
    }

    li:not(:first-child) {
      margin-left: 1rem;
    }

    img {
      max-height: 360px;
    }
  }
</style>
