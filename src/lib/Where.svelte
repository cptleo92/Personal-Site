<script>
  import FaGithubSquare from "svelte-icons/fa/FaGithubSquare.svelte";
  import FaLinkedin from "svelte-icons/fa/FaLinkedin.svelte";
  import FaAngellist from "svelte-icons/fa/FaAngellist.svelte";
  import MdEmail from "svelte-icons/md/MdEmail.svelte";
</script>

<section>
  <img
    id="Where"
    class="heading"
    src="images/where.svg"
    alt="where to find me"
  />

  <h4>Please don't hesitate to reach out!</h4>
  <p>
    Connect with me on LinkedIn or send me an email! I'm open to all
    opportunities, collaborations, and regular old chats.
  </p>

  <div class="icon-container">
    <a
      href="https://www.linkedin.com/in/sirleoc"
      target="_blank"
      rel="noreferrer"
      class="icon"
    >
      <FaLinkedin />
    </a>

    <a
      href="https://www.github.com/cptleo92"
      target="_blank"
      rel="noreferrer"
      class="icon"
    >
      <FaGithubSquare />
    </a>

    <a
      href="https://angel.co/u/leo-cheng-8"
      target="_blank"
      rel="noreferrer"
      class="icon"
    >
      <FaAngellist />
    </a>

    <a href="mailto:leo.cheng92@gmail.com" target="_blank" class="icon">
      <MdEmail />
    </a>
  </div>

  <button><a href="Leo_Cheng_SE_Resume.pdf">My Resume</a></button>
</section>

<style>
  section {
    height: 90vh;
  }

  .icon-container {
    display: flex;
    margin: auto;
    padding: 1rem 0 2rem 0;
    justify-content: space-around;
  }

  .heading {
    padding-top: 4rem;
    width: 100%;
    margin: 2rem 0;
  }

  .icon {
    width: 40px;
    height: 40px;
  }

  .icon:hover {
    opacity: 60%;
    transition: opacity 0.2s ease-in;
  }

  p {
    font-size: 0.8rem;
    margin: 0.5rem 1rem 2rem 0;
  }

  button {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 1.5rem auto;
    min-width: 160px;
    height: 60px;
    background-color: transparent;
    border: 2px solid #ffffff;
    border-radius: 15px;
    color: white;
    font-family: Roboto;
    font-size: 1.5rem;
    cursor: pointer;
  }

  button:hover {
    scale: 103%;
    transition: scale 0.2s ease-out;
  }

  button:active {
    scale: 95%;
    transition: scale 0.2s ease-out;
  }
</style>
