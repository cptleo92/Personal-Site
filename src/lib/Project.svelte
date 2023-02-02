<script>
  export let project;

  import { DiGithubBadge } from "svelte-icons/di";
  import FaExternalLinkAlt from "svelte-icons/fa/FaExternalLinkAlt.svelte";
</script>

<section>
  <img src={project.preview} alt={`${project.title} preview`} />

  <div class="description">
    <div class="project-text">
      <h2>{project.title}</h2>
      <p>{project.description}</p>
    </div>

    <div class="tools">
      <h2>Tools</h2>
      <ul>
        {#each project.tools as tool}
          <li>{tool}</li>
        {/each}
      </ul>
    </div>
  </div>

  <hr />

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
    max-height: 100%;
    object-fit: contain;
  }

  p {
    font-weight: 300;
    font-size: 0.7rem;
    margin: 1rem 0;
  }

  .project-text {
    padding: 0.7rem;
    width: 50%;
    background-color: #242d30;
  }

  .icon-container {
    display: flex;
    width: 40%;
    margin: auto;
    padding: 1rem 0 2rem 0;
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
    margin-top: -4px;
  }

  .tools {
    /* border-left: 1px solid white; */
    width: 50%;
    padding: 0.7rem;
    background-color: #334044;
  }

  hr {
    margin: 1rem 3rem;
  }

  ul {
    padding-left: 1rem;
    margin: 1rem 0;
  }

  li {
    /* margin-right: 2rem; */
    font-size: 0.7rem;
    font-weight: 300;
    list-style: disc;
  }

  /* li:first-child {
    list-style: none;
  } */
</style>
