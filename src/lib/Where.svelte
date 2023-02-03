<script>
  import FaGithubSquare from "svelte-icons/fa/FaGithubSquare.svelte";
  import FaLinkedin from "svelte-icons/fa/FaLinkedin.svelte";
  import FaAngellist from "svelte-icons/fa/FaAngellist.svelte";
  import MdEmail from "svelte-icons/md/MdEmail.svelte";
  import { onMount } from "svelte";

  let transition = false;

  let options = {
    threshold: 1,
  };

  onMount(() => {
    let observer = new IntersectionObserver((entries, observer) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          transition = true;
          observer.unobserve(entry.target);
        }
      });
    }, options);

    let section = document.querySelector(".box");
    observer.observe(section);
  });
</script>

<section>
  <img
    id="Contact"
    class="heading"
    src="images/where.svg"
    alt="where to find me"
  />

  <div
    class="box"
    style={transition && "opacity: 1; transform: translateY(0);"}
  >
    <h3>Please don't hesitate to reach out!</h3>
    <p>
      Connect with me on LinkedIn or send me an email! <br /> I'm open to all opportunities,
      collaborations, and regular old chats.
    </p>

    <div class="icon-container">
      <a
        href="https://www.linkedin.com/in/sirleoc"
        target="_blank"
        rel="noreferrer"
        class="icon slide-1"
        style={transition && "opacity: 1; transform: translateY(0);"}
      >
        <FaLinkedin />
      </a>

      <a
        href="https://www.github.com/cptleo92"
        target="_blank"
        rel="noreferrer"
        class="icon slide-2"
        style={transition && "opacity: 1; transform: translateY(0);"}
      >
        <FaGithubSquare />
      </a>

      <a
        href="https://angel.co/u/leo-cheng-8"
        target="_blank"
        rel="noreferrer"
        class="icon slide-3"
        style={transition && "opacity: 1; transform: translateY(0);"}
      >
        <FaAngellist />
      </a>

      <a
        href="mailto:leo.cheng92@gmail.com"
        target="_blank"
        class="icon slide-4"
        style={transition && "opacity: 1; transform: translateY(0);"}
      >
        <MdEmail />
      </a>
    </div>

    <button><a href="Leo_Cheng_SE_Resume.pdf">My Resume</a></button>
  </div>
</section>

<style>
  section {
    height: 100vh;
  }

  .box {
    opacity: 0;
    transform: translateY(50px);
    transition: all 300ms ease-out;
  }

  .icon-container {
    display: flex;
    margin: auto;
    padding: 1rem 0 2rem 0;
    justify-content: space-around;
  }

  .heading {
    padding-top: 4rem;
    width: 90%;
    margin: 4rem 0;
  }

  .icon {
    width: 40px;
    height: 40px;
    opacity: 0;
    transform: translateY(50px);
  }

  .slide-1 {
    transition: all 300ms ease-out;
  }

  .slide-2 {
    transition: all 300ms ease-out 100ms;
  }

  .slide-3 {
    transition: all 300ms ease-out 200ms;
  }

  .slide-4 {
    transition: all 300ms ease-out 300ms;
  }

  .icon:hover {
    opacity: 60%;
    transition: opacity 0.2s ease-in;
  }

  h3 {
    color: #9ab4b9;
  }

  p {
    margin: 2rem 1rem 5rem 0;
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
